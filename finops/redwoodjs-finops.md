# RedwoodJS FinOps

RedwoodJS is a free, open-source framework. The financial considerations for running a RedwoodJS application are driven entirely by the hosting platform and third-party services integrated into the application, not by framework licensing fees.

## Cost Centers

### Hosting / Compute

The RedwoodJS GraphQL function and any background jobs run as serverless functions or traditional Node.js servers. Key cost drivers:

| Platform | Free Tier | Paid Starting Point |
|---|---|---|
| Netlify | 125k function invocations/month | $19/month (Pro) |
| Vercel | 100 GB-hours execution/month | $20/month (Pro) |
| Render | 750 hrs/month (free instance sleeps) | $7/month (Starter) |
| Fly.io | 3 shared-cpu-1x VMs free | ~$2–5/month per VM |
| AWS (Lambda + RDS) | 1M Lambda invocations free | Variable; RDS minimum ~$15/month |
| Cloudflare Workers (rwsdk) | 100k req/day free | $5/month (Workers Paid) |

### Database (Prisma-backed)

RedwoodJS uses Prisma as its ORM. The database itself is external:

| Service | Free Tier | Notes |
|---|---|---|
| PlanetScale | Hobby free (1 DB) | MySQL-compatible; branching |
| Neon | 0.5 GB free | Serverless Postgres |
| Supabase | 500 MB free | Postgres + Auth + Storage |
| Railway | $5 credit/month | Postgres, MySQL, Redis |
| AWS RDS / Aurora | No permanent free tier | Aurora Serverless v2 scales to zero |

### Authentication

RedwoodJS supports multiple auth providers. Cost varies by provider:

- **dbAuth** (built-in): No third-party cost; storage in your database.
- **Clerk**: Free up to 10k MAU; $25/month thereafter.
- **Auth0**: Free up to 7.5k MAU; paid plans from $23/month.
- **Supabase Auth**: Included in Supabase free tier.

### CDN / Static Assets

The React front-end is a static build. Hosting on Netlify, Vercel, or Cloudflare Pages is typically free for most traffic levels under standard plans.

## Cost Optimization Tips

1. Use serverless platforms (Netlify, Vercel, Cloudflare Workers) to pay only for actual invocations rather than always-on servers.
2. Enable Trusted Documents (persisted operations) to reduce GraphQL parsing overhead per request.
3. Leverage Apollo Client's in-memory cache on the front end to reduce redundant GraphQL calls.
4. Use Prisma's connection pooling (PgBouncer via Prisma Accelerate or Supabase's built-in pooler) to avoid database connection exhaustion on serverless deployments.
5. Set query complexity and depth limits via GraphQL Armor to prevent runaway queries that inflate compute costs.

## References

- https://redwoodjs.com/docs/deploy/introduction
- https://www.prisma.io/pricing
- https://clerk.com/pricing
- https://netlify.com/pricing
- https://vercel.com/pricing
