# RedwoodJS Rate Limits

RedwoodJS is a self-hosted, open-source framework. There are no centrally enforced rate limits imposed by the RedwoodJS project itself. Rate limiting is the responsibility of the application developer and the hosting platform.

## Framework-Level Protections

RedwoodJS bundles GraphQL Armor via the Envelop plugin system, which provides the following default protections against abuse:

| Protection | Default Behavior |
|---|---|
| Query depth limiting | Configurable; protects against deeply nested query attacks |
| Query complexity limiting | Configurable; blocks overly expensive queries |
| Introspection | Disabled automatically in production |
| GraphiQL | Disabled automatically in production |
| Persisted Operations (Trusted Documents) | Optional; restricts API to pre-approved query hashes |
| CORS | Configurable per deployment |

## Hosting-Platform Rate Limits

Actual request rate limits are enforced by the platform you deploy to:

| Platform | Notes |
|---|---|
| Netlify Functions | 125k requests/month free; paid plans scale up |
| Vercel Functions | 100 GB-hours free; scales with Pro/Enterprise |
| Render | Depends on chosen plan (free to enterprise) |
| Fly.io | Based on VM size and network egress |
| AWS Lambda | 1M free requests/month; standard Lambda pricing thereafter |
| Cloudflare Workers (rwsdk) | 100k requests/day free; $5/month for 10M requests |

## Recommendations for Application Developers

- Use GraphQL Armor settings in `redwood.toml` or the GraphQL handler config to set depth and complexity limits appropriate for your schema.
- Add an upstream rate-limiting layer (e.g., Cloudflare WAF, AWS WAF, or an API Gateway) in front of the `/graphql` endpoint in production.
- Consider enabling Trusted Documents (persisted operations) to prevent arbitrary query execution.
- Use `@requireAuth` directives on all resolvers; never rely solely on network-level rate limiting.

## References

- https://docs.redwoodjs.com/docs/graphql#security
- https://docs.redwoodjs.com/docs/graphql#trusted-documents
- https://the-guild.dev/graphql/armor
