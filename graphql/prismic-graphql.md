---
generated: '2026-08-13'
method: probed
source: https://prismic-main.cdn.prismic.io/graphql
---

# Prismic GraphQL API

The Prismic GraphQL API is a read-only endpoint that exposes structured content stored in a Prismic repository. It supports deep and selective content fetching, Relay-style cursor pagination, filtering, and sorting.

**Endpoint:** `https://{your-repo-name}.cdn.prismic.io/graphql`

**Explorer:** `https://{your-repo-name}.prismic.io/graphql`

**Documentation:** https://prismic.io/docs/graphql-technical-reference

## The schema is per-repository and dynamic

Every custom type and shared slice defined in a repository generates its own object types, `Where*` input filters, `Sort*` enums and `Query` root fields **at runtime**. There is no single Prismic GraphQL schema — there is one per repository.

Full anonymous introspection against Prismic's own public repository on 2026-08-13 returned **6,133 types**, of which **6,118 were specific to that repository's content model**. The remaining 15 are the built-in base schema present in every repository, captured verbatim in [`prismic-base-schema.graphql`](prismic-base-schema.graphql):

- **Scalars** — `Date`, `DateTime`, `Json`, `Long`
- **Interfaces** — `_Document` (`_meta`), `_Linkable` (`_linkType`)
- **Link types** — `_ExternalLink`, `_FileLink`, `_ImageLink`
- **Metadata** — `Meta` (id, uid, type, tags, lang, alternateLanguages, firstPublicationDate, lastPublicationDate)
- **Pagination** — `PageInfo`, `_DocumentEdge`, `_DocumentConnection`
- **Sorting** — `SortDocumentsBy`
- **Root field** — `_allDocuments`, the only Query field present in every repository

## Calling it

Prismic's GraphQL endpoint is unusual in three ways an agent will trip over:

1. **GET, not POST.** Queries are sent as GET requests. `@prismicio/client` exposes `graphQLFetch` precisely so Apollo (`useGETForQueries: true`) and `graphql-request` (`method: "get"`) can be configured for it.
2. **A `Prismic-Ref` header is required.** The ref names the version of the repository's content to query, and is fetched first from the Repository API at `https://{repo}.cdn.prismic.io/api/v2`. A new master ref is minted on every publish.
3. **Read-only.** There is no mutation root and no subscription root. Writes go through the Migration API, the Types API, the CLI or the MCP server.

Public ("Open API") repositories answer anonymously. Private repositories require `Authorization: Bearer <access-token>`.

## Verified live

| Probe | Result |
|---|---|
| `GET https://prismic-main.cdn.prismic.io/api/v2` | 200 — master ref `an3eUxEAACcAexk-` |
| `GET .../graphql?query={__schema{queryType{name}}}` + `Prismic-Ref` | 200 — `{"data":{"__schema":{"queryType":{"name":"Query"}}}}` |
| Full introspection | 200 — 6,133 types, 91 Query root fields |

## Root field patterns

| Query kind | Root field |
|---|---|
| All documents | `_allDocuments` |
| All by type | `all{Type_id}s` — snake_cased API ID, first letter capitalized, pluralized (e.g. `allBlog_posts`) |
| Single document | `{type_id}(uid: "...", lang: "...")` |

Pagination is Relay-style: `first`/`last`/`before`/`after` with `pageInfo`, `edges`, `node`, `cursor` and `totalCount`. The maximum page size is 100.

## References

- Documentation: https://prismic.io/docs/graphql-technical-reference
- API References index: https://prismic.io/docs/apis
- GitHub: https://github.com/prismicio
- SDL: [`prismic-base-schema.graphql`](prismic-base-schema.graphql)
- Conventions: [`../conventions/prismic-conventions.yml`](../conventions/prismic-conventions.yml)
