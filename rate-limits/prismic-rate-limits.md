# Prismic Rate Limits

Prismic enforces rate limits on its Content API and GraphQL API to ensure
platform stability and fair usage across all repositories.

## Content API Rate Limits

- **Uncached requests**: 200 requests per second per repository
- **Cached CDN requests**: No rate limit (served directly from CDN edge nodes)

CDN caching is strongly recommended for production workloads. Queries hitting
the `.cdn.prismic.io` endpoint are cached and do not count against the
per-second rate limit.

## Monthly API Call Quotas by Plan

| Plan       | Monthly API Calls        |
|------------|--------------------------|
| Free       | 4 million                |
| Starter    | 4 million                |
| Small      | 4 million                |
| Medium     | 5 million                |
| Platinum   | 10 million (soft limit)  |
| Platinum   | 50 million (hard limit)  |
| Enterprise | Custom                   |

## GraphQL API

The GraphQL API endpoint (`https://{repo}.cdn.prismic.io/graphql`) follows
the same rate limiting rules as the Content API. Pagination is limited to
a maximum of 100 items per query using `first` or `last` arguments.

## What Happens When You Hit the Limit

- Exceeding the per-second rate limit returns HTTP 429 (Too Many Requests).
- Exceeding monthly API call quotas may result in service interruption or
  automatic plan upgrade prompts depending on the plan tier.

Source: https://prismic.io/docs/content-api
Source: https://community.prismic.io/t/prismic-api-limits-and-cdn-bandwidth-explained-faq-guide/16707
