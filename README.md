# Prismic

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

Prismic is a headless CMS and page builder that lets marketing teams create and
manage website content independently while developers work in their preferred
stack. Content is modelled as custom types and reusable "slices", authored in a
visual Page Builder or locally in Slice Machine, and delivered over a CDN-backed
API. Prismic runs seven public HTTP APIs across four hosts: a Content API and
Repository API for reads, a beta Tags API, a Types API for content models, an
Asset API for the media library, a Migration API for bulk content creation, and
a read-only GraphQL endpoint whose schema is generated per repository from the
customer's own content model. Every read is addressed to a content "ref" naming
a specific published version. Prismic also ships a first-party CLI, a published
Agent Skill, and a remote OAuth-protected MCP server with sixteen tools, and
supports Next.js, Nuxt and SvelteKit with first-party rendering components.

**Areas:** GraphQL · Headless CMS · Content Management · Page Builder · JAMstack · Marketing · Content Delivery · Developer Tools · MCP · Webhook · Localization · Digital Asset Management

## Prismic on APIs.io

Everything profiled for Prismic is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/prismic/](https://apis.io/providers/prismic/)** — or go straight to one of the APIs or properties below.

### APIs (8)

- [Prismic Content API](https://apis.io/apis/prismic/content-api/) — The Content API is Prismic's primary read surface. It queries published documents from a repository with a bracketed filter language (`q`), orderings,…
- [Prismic Repository API](https://apis.io/apis/prismic/repository-api/) — The Repository API is the gateway to a Prismic repository. A single unauthenticated GET returns the repository's available refs (including the master ref…
- [Prismic GraphQL API](https://apis.io/apis/prismic/graphql-api/) — A read-only GraphQL endpoint for deep and selective fetching of content from a Prismic repository. The schema is generated per repository: every custom type…
- [Prismic Types API](https://apis.io/apis/prismic/types-api/) — The Types API reads and writes a repository's content models — custom types and Slice Machine shared slices — as JSON. It is how content models are backed…
- [Prismic Asset API](https://apis.io/apis/prismic/asset-api/) — The Asset API manages a repository's media library: list and search assets by keyword, upload a new asset as multipart form data, patch its alt text, notes…
- [Prismic Migration API](https://apis.io/apis/prismic/migration-api/) — The Migration API creates and updates Prismic pages programmatically, using the same document shape the Content API returns. Everything it writes lands in a…
- [Prismic Tags API](https://apis.io/apis/prismic/tags-api/) — A single-endpoint beta API that returns every tag used across a repository's pages, including tags on drafts and pages staged in releases, as a flat array.…
- [Prismic MCP Server](https://apis.io/apis/prismic/mcp/) — A remote, OAuth-protected Model Context Protocol server that lets an AI assistant search, read, create and publish Prismic content in conversation. Sixteen…

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### AsyncAPI (1)

Event-driven and webhook contracts.

- [Prismic Webhooks](https://apis.io/asyncapis/prismic/prismic-webhooks/)

#### GraphQL (1)

GraphQL schemas.

- [Prismic GraphQL API](https://apis.io/graphqls/prismic/prismic-graphql/)

#### MCP servers (1)

Model Context Protocol servers that expose the API to agents.

- [Prismic MCP Server](https://apis.io/servers/prismic/prismic-mcp-server/)

#### Security (4)

Authentication, trust centre, and vulnerability disclosure.

- [Prismic Authentication](https://apis.io/security/prismic/prismic-authentication/)
- [Prismic Domain Security](https://apis.io/security/prismic/prismic-domain-security/)
- [Prismic Trust Center](https://apis.io/security/prismic/prismic-trust-center/)
- [Prismic Vulnerability Disclosure](https://apis.io/security/prismic/prismic-vulnerability-disclosure/)

#### Plans and pricing (1)

Published plans, tiers and prices.

- [Prismic Plans Pricing](https://apis.io/plans/prismic/prismic-plans-pricing/)

#### Rate limits (1)

Published request limits.

- [Prismic Rate Limits](https://apis.io/rate-limits/prismic/prismic-rate-limits/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://prismic.io)
- [Documentation](https://prismic.io/docs)
- [Getting started](https://prismic.io/docs/nextjs)
- [API reference](https://prismic.io/docs/apis)
- [Pricing](https://prismic.io/pricing)
- [Sign up](https://prismic.io/dashboard/signup)
- [Support](https://prismic.io/docs/help-center)
- [Changelog](https://prismic.io/updates)
- [Blog](https://prismic.io/blog)
- [Security](https://prismic.io/legal/security)
- [Terms of service](https://prismic.io/legal/terms-of-service)
- [Privacy policy](https://prismic.io/legal/privacy)
- [GitHub](https://github.com/prismicio)
- [Status](https://status.prismic.io/)

## API Evangelist rating

**Kin Score 71.2** — exemplar · rubric 0.25.0 · scored 2026-10-23

| Facet | Score |
|---|---|
| Discoverability | 86.7 |
| Contract quality | 45.8 |
| Contract governance | 18.2 |
| Operational transparency | 84.2 |
| Developer ergonomics | 90.5 |
| Access clarity | 84.2 |

**Agent readiness 53.6** — agent-ready (gated down from agent-native)

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | — |
| Reversibility Documented | — |
| MCP Server | verified |
| Auth Clarity | served (partial credit) |
| Idempotency | — |
| Error Semantics | documented (partial credit) |
| OpenAPI Examples | — |
| Rate Limit Signal | documented (partial credit) |
| Event Surface Described | yes |
| Agent Skills | yes |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | served (partial credit) |
| Protected Resource Metadata | verified |
| Dynamic Client Registration | yes |
| Agentic Commerce | — |
| Pagination Ratio | na |
| Operation Distinctiveness | na |

**Regulatory alignment 35.3** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/prismic/](https://apis.io/providers/prismic/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Prismic: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/prismic/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
