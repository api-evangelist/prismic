# Prismic GraphQL API

The Prismic GraphQL API is a read-only endpoint that exposes structured content stored in a Prismic repository. It supports deep and selective content fetching, cursor-based pagination, filtering, and sorting. Because Prismic uses per-repository endpoints and GET-based requests (with a required `Prismic-Ref` header), each repository exposes its own GraphQL schema that includes dynamically generated types for every custom content type defined in that repository. The schema includes built-in base types for documents, links, images, slices, and metadata that are common across all repositories.

Authentication uses an access token passed via the `Authorization` header for private repositories. Public repositories can be queried without authentication.

**Endpoint:** https://{your-repo-name}.cdn.prismic.io/graphql

**Explorer:** https://{your-repo-name}.prismic.io/graphql

**Documentation:** https://prismic.io/docs/graphql-technical-reference

**References:**

- Documentation: https://prismic.io/docs/graphql-technical-reference
- GettingStarted: https://prismic.io/docs/technologies/graphql
- GitHub: https://github.com/prismicio
