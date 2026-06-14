# Prismic FinOps

Financial operations guidance for managing Prismic CMS costs at scale.

## Cost Drivers

### API Call Volume
Monthly API call quotas are the primary cost driver. Each plan tier includes
a fixed monthly allowance. Exceeding the quota can trigger overage charges or
force a plan upgrade.

- Free / Starter / Small: 4 million calls/month
- Medium: 5 million calls/month
- Platinum: 10–50 million calls/month (soft/hard limits)

### Bandwidth
CDN bandwidth is bundled into each plan. High-traffic sites serving large
media-rich documents should monitor bandwidth consumption, particularly on
lower-tier plans.

### Repository Count
Pricing is per repository. Organizations running multiple brands, regions, or
environments (staging/production) will incur costs for each active repository
beyond what may be included in a plan.

### Users and Roles
Higher-tier plans unlock additional user seats and role-based access control.
Team size and the need for granular permissions should be factored into plan selection.

## Cost Optimization Strategies

1. **Maximize CDN cache hit rate**: Route all production traffic through the
   `.cdn.prismic.io` GraphQL endpoint. Cached requests do not count against
   monthly API call quotas or per-second rate limits.

2. **Use selective fetching**: GraphQL allows you to fetch only the fields you
   need, reducing payload sizes and unnecessary query overhead.

3. **Consolidate repositories**: Where possible, use a single repository with
   multiple locales rather than separate repositories per locale to stay within
   a single plan tier.

4. **Monitor usage via dashboard**: Prismic's repository dashboard provides
   visibility into API call consumption and bandwidth to catch overages early.

5. **Right-size the plan**: Start on Free or Starter for development and only
   upgrade to Medium/Platinum when production traffic justifies the cost.

## Pricing Reference

| Plan       | Monthly Price | API Calls/Month       |
|------------|---------------|-----------------------|
| Free       | $0            | 4 million             |
| Starter    | $10           | 4 million             |
| Small      | $25           | 4 million             |
| Medium     | $150          | 5 million             |
| Platinum   | $675          | 10M (soft) / 50M (hard) |
| Enterprise | Custom        | Custom                |

Source: https://prismic.io/pricing
