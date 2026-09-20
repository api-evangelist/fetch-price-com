---
name: fetch-price-register-and-search
description: "Register an agent with fetch-price to get an fp_ API key (and optionally your own eBay Partner Network campaign id for BYOK affiliate routing), then run keyed UK product searches and handle the result_type, rate-limit and error rules. Use when an agent needs more than the keyless 50 lookups/month, needs its own affiliate tracking, or must present marketplace results to a person honestly."
api: openapi/fetch-price-com-openapi.yml
operations: [registerAgent, queryProducts, getHealth]
generated: '2026-09-19'
method: generated
source: https://fetch-price.com/docs/
---

# Register an agent, then search with a key

Base URL: `https://api.fetch-price.com`. Everything is JSON over HTTPS. The API is UK-only, GBP-only,
physical marketplace listings only (eBay UK live; Amazon UK returns a tracked search link until its API
access lands).

## 1. Decide whether you need a key

- No key: `queryProducts` works anonymously on the free tier - 50 lookups/month, counted per IP, 30
  requests/minute. Returned links carry fetch-price's own affiliate tag.
- Key: raises the monthly quota to the plan's (Pro 5,000; Scale/Trade unlimited) and, on a paid plan,
  routes affiliate commission to YOUR eBay Partner Network account (BYOK). Get one with `registerAgent`.

## 2. Register once (`registerAgent`, POST /api/agents/register)

All four of `name`, `owner` (email), `networks`, `endpoint` (your agent's URL) are required;
`commission_split` is optional. Put your EPN `campaign_id` under `networks.ebay_uk` if you have one;
otherwise send an empty object per network and links run on fetch-price's tag.

Response: `{agent_id: "agent-...", api_key: "fp_...", tier: "free", query_limit: 50}`. The key is also
emailed to `owner`. Store it as a credential: the provider never shows it again in a public response, and
revocation or account deletion is by email to the provider (privacy page), not by API. There is no
DELETE endpoint - registering is not reversible from the API.

## 3. Search (`queryProducts`, POST /api/query)

Send the key as `X-API-Key: fp_...` (SDK style) or `Authorization: Bearer fp_...` (MCP/SKILL.md style).
Body: `query` (required, <= 200 chars, natural language - "quiet portable air con for a bedroom" beats
"air conditioner"), `max_results` (1-20, default 5, per network), `max_price` (GBP), `networks`
(`["ebay_uk"]`, `["amazon_uk"]` or omit for both - never send an empty array).

Read `results[]` and `meta`:
- `result_type: item` - a real listing: `product`, `price`, `currency`, `condition`, `network`,
  `item_id`, `image`, `url`. Present `url` to the user UNCHANGED; it is the affiliate-tracked buy link.
- `result_type: search_link` - a tracked marketplace search URL with `price: 0`. NEVER present it as a
  product; say "no live listings from <network>, here is a search link" or drop it.
- Results arrive in the marketplace's own order; the provider does not re-rank by commission.

Pass the affiliate disclosure on when you show results to a person: purchase links are
affiliate-tracked and the marketplace pays fetch-price (or you, under BYOK) a commission at no cost to
the buyer (https://fetch-price.com/privacy).

## 4. Errors, limits, retries

- `400 {"error":"query required","results":[]}` - fix the body; do not retry as-is.
- `401` - key rejected: check the header, or register again.
- `429` - 30/min per key or IP, or the monthly quota: read `X-RateLimit-Remaining` on every response and
  back off before you hit 0; on 429 wait for the next minute window (no Retry-After header is documented).
- `405` on GET /api/query - it is POST-only.
- Empty `results` with `meta.returned: 0` - retry ONCE with a broader query, then tell the user nothing
  was found. If two calls in a row fail, call `getHealth` (GET /health) and check `ebay_live`.

## 5. What this API will not do

No idempotency keys, no pagination beyond `max_results`, no webhooks, no price history, no non-UK
marketplaces, no digital goods. Every search POST consumes one lookup of quota even when the query is
identical to the last one, so cache on your side.
