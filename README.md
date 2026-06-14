# RedwoodJS

RedwoodJS is an opinionated, full-stack JavaScript/TypeScript web application framework designed to take you from side project to startup. It combines React on the front end with a GraphQL API layer on the back end, backed by Prisma ORM, and is designed for serverless deployment.

## Overview

- **Website:** https://redwoodjs.com
- **Documentation:** https://docs.redwoodjs.com/docs/introduction
- **GitHub:** https://github.com/redwoodjs
- **Community:** https://community.redwoodjs.com
- **Discord:** https://discord.gg/redwoodjs
- **LinkedIn:** https://www.linkedin.com/company/redwoodjs

## Key Features

- Schema-first GraphQL API via GraphQL Yoga + Envelop
- Automatic SDL generation and resolver wiring
- Prisma ORM for database access (PostgreSQL, MySQL, SQLite)
- React front end with Apollo Client pre-configured
- Directive-based authorization (`@requireAuth`, `@skipAuth`)
- GraphQL Armor security by default (depth limiting, complexity limiting, introspection off in production)
- Trusted Documents (persisted operations) support
- CLI tooling (`yarn rw`) for code generation, migrations, and deploys
- Storybook and Jest integrations
- Deploy targets: Netlify, Vercel, Render, Fly.io, AWS, Baremetal

## GraphQL API

The RedwoodJS GraphQL API is available at `/graphql` in any Redwood application. It is powered by GraphQL Yoga and uses SDL files (`*.sdl.ts`) to define the schema. Service functions serve as resolvers and integrate directly with Prisma.

See [graphql/redwoodjs-graphql.md](graphql/redwoodjs-graphql.md) for a full technical reference.

## Repository Contents

| Path | Description |
|---|---|
| `apis.yml` | APIs.json 0.19 catalog entry |
| `graphql/redwoodjs-graphql.md` | GraphQL API reference |
| `plans/redwoodjs-plans.md` | Pricing and plan information |
| `rate-limits/redwoodjs-rate-limits.md` | Rate limiting details |
| `finops/redwoodjs-finops.md` | FinOps and cost analysis |

## Maintainer

Kin Lane — kin@apievangelist.com
