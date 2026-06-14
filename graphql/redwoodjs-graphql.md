# RedwoodJS GraphQL API

## Overview

RedwoodJS provides a built-in GraphQL API layer powered by **GraphQL Yoga** and the **Envelop** plugin system. The API follows a schema-first, "deconstructed" approach where SDL files define the schema and service functions act as resolvers.

## Default Endpoint

```
/graphql
```

Health check:

```
/graphql/health
```

## Architecture

```
Client (Apollo Client)
       │
       ▼
  /graphql endpoint (GraphQL Yoga)
       │
       ▼
  SDL Files (*.sdl.ts)  ──►  Type definitions, queries, mutations
       │
       ▼
  Service Functions  ──►  Resolvers (Prisma ORM calls, business logic)
       │
       ▼
  Prisma ORM  ──►  Database (PostgreSQL, MySQL, SQLite, etc.)
```

## Schema-First Development

Define your schema in an SDL file:

```graphql
# api/src/graphql/posts.sdl.ts
type Post {
  id: Int!
  title: String!
  body: String!
  createdAt: DateTime!
}

type Query {
  posts: [Post!]! @requireAuth
  post(id: Int!): Post @requireAuth
}

type Mutation {
  createPost(input: CreatePostInput!): Post! @requireAuth
  updatePost(id: Int!, input: UpdatePostInput!): Post! @requireAuth
  deletePost(id: Int!): Post! @requireAuth
}
```

Redwood automatically wires the SDL to a service file at `api/src/services/posts/posts.ts`.

## Security

All queries and mutations must be decorated with one of:

- `@requireAuth` — requires an authenticated session
- `@skipAuth` — explicitly marks a resolver as public
- Custom directives for field-level authorization

GraphQL Armor is enabled by default and provides:

- Query depth limiting
- Query complexity limiting
- Introspection disabled in production
- GraphiQL disabled in production

## Trusted Documents (Persisted Operations)

RedwoodJS supports Trusted Documents to restrict the API to a pre-approved set of query hashes, preventing arbitrary query execution in production.

## Plugins (Envelop)

The GraphQL handler is extensible via Envelop plugins configured in `api/src/functions/graphql.ts`:

```typescript
import { createGraphQLHandler } from '@redwoodjs/graphql-server'

export const handler = createGraphQLHandler({
  loggerConfig: { logger, options: {} },
  directives,
  sdls,
  services,
  onException: () => db.$disconnect(),
})
```

## Apollo Client Integration

The web side uses `RedwoodApolloProvider` which wraps Apollo Client with sensible defaults including an in-memory cache and automatic authentication header injection.

## References

- https://docs.redwoodjs.com/docs/graphql
- https://the-guild.dev/graphql/yoga-server
- https://the-guild.dev/graphql/envelop
- https://the-guild.dev/graphql/armor
