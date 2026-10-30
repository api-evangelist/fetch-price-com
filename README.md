# POLICYANDPLAY LTD

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

POLICYANDPLAY LTD (England & Wales, company no. 17253846) operates fetch-price, a UK product and price search API built for AI agents: one POST to api.fetch-price.com returns live eBay UK listings (via the official Browse API; Amazon UK rolling out) as normalised JSON with GBP prices, condition and an affiliate-tracked purchase URL. The free tier needs no API key (50 lookups/month, 30 requests/minute); Pro (GBP 29) and Scale/Trade (GBP 99) plans raise quotas and let customers route affiliate commission to their own eBay Partner Network account. The same API is exposed as a conformant A2A 1.0.0 agent card with a live JSON-RPC message/send binding, a stdio MCP server listed in the official MCP registry, a provider-authored SKILL.md, llms.txt, and npm/PyPI SDKs. No OpenAPI is published; the profile's spec was generated by API Evangelist from the provider's own reference and checked against the live host.

**Areas:** Company · Price Comparison · Product Search · E-Commerce · Affiliates · Marketplace · Shopping · eBay · United Kingdom · AI Agents · A2A · MCP

## POLICYANDPLAY LTD on APIs.io

Everything profiled for POLICYANDPLAY LTD is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/fetch-price-com/](https://apis.io/providers/fetch-price-com/)** — or go straight to one of the APIs or properties below.

### APIs (4)

- [fetch-price A2A Agent](https://apis.io/apis/fetch-price-com/fetch-price-a2a-agent/) — Agent-to-Agent surface declared by the A2A 1.0.0 agent card at https://fetch-price.com/.well-known/agent-card.json (also served at the legacy agent.json…
- [POLICYANDPLAY LTD Agents API](https://apis.io/apis/fetch-price-com/fetch-price-com-agents-api/) — Agent registration and API key issuance
- [POLICYANDPLAY LTD Products API](https://apis.io/apis/fetch-price-com/fetch-price-com-products-api/) — Live UK marketplace product and price search
- [POLICYANDPLAY LTD Service API](https://apis.io/apis/fetch-price-com/fetch-price-com-service-api/) — Health and public statistics

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [fetch-price-com-mcp.yml](https://apis.io/servers/fetch-price-com/fetch-price-com-mcp-yml/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Fetch Price Com Agentic Access](https://apis.io/agentic-access/fetch-price-com/fetch-price-com-agentic-access/)

#### JSON Schema (6)

The data models the API reads and writes.

- [Health](https://apis.io/schemas/fetch-price-com/fetch-price-com-health/)
- [QueryRequest](https://apis.io/schemas/fetch-price-com/fetch-price-com-query-request/)
- [QueryResponse](https://apis.io/schemas/fetch-price-com/fetch-price-com-query-response/)
- [RegisterAgentRequest](https://apis.io/schemas/fetch-price-com/fetch-price-com-register-agent-request/)
- [RegisterAgentResponse](https://apis.io/schemas/fetch-price-com/fetch-price-com-register-agent-response/)
- [Stats](https://apis.io/schemas/fetch-price-com/fetch-price-com-stats/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Fetch Price Com Context](https://apis.io/jsonld/fetch-price-com/fetch-price-com-context/)

#### Governance rules (1)

Spectral rulesets for the provider's contracts.

- [POLICYANDPLAY LTD API Rules](https://apis.io/rules/fetch-price-com/fetch-price-com-rules/)

#### Security (2)

Authentication, trust centre, and vulnerability disclosure.

- [Fetch Price Com Authentication](https://apis.io/security/fetch-price-com/fetch-price-com-authentication/)
- [Fetch Price Com Domain Security](https://apis.io/security/fetch-price-com/fetch-price-com-domain-security/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Fetch Price Com Plans Pricing](https://apis.io/plans/fetch-price-com/fetch-price-com-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Fetch Price Com Rate Limits](https://apis.io/rate-limits/fetch-price-com/fetch-price-com-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://fetch-price.com/)
- [Documentation](https://fetch-price.com/docs/)
- [Getting started](https://fetch-price.com/docs/#quickstart)
- [API reference](https://fetch-price.com/docs/#endpoints)
- [Pricing](https://fetch-price.com/docs/#pricing)
- [Sign up](https://fetch-price.com/docs/#get-key)
- [Privacy policy](https://fetch-price.com/privacy)

## API Evangelist rating

**Kin Score 51.3** — developing · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 68.3 |
| Contract quality | 28.5 |
| Contract governance | 35.6 |
| Operational transparency | 44.7 |
| Developer ergonomics | 64.3 |
| Access clarity | 65.8 |

**Agent readiness 52.3** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | yes |
| Reversibility Documented | — |
| MCP Server | documented (partial credit) |
| Auth Clarity | bearer (partial credit) |
| Idempotency | — |
| Error Semantics | verified |
| OpenAPI Examples | verified |
| Rate Limit Signal | verified |
| Event Surface Described | — |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | conformant |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | distinct |

**Regulatory alignment 28.4** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/fetch-price-com/](https://apis.io/providers/fetch-price-com/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for POLICYANDPLAY LTD: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/fetch-price-com/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
