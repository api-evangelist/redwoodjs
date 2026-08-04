# RedwoodJS

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
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
