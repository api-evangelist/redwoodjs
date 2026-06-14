# RedwoodJS GraphQL API

RedwoodJS exposes a schema-first GraphQL API powered by GraphQL Yoga and the Envelop plugin system. SDL files (*.sdl.ts) declare types, queries, and mutations while service functions serve as resolvers. Redwood merges them automatically at startup into a single executable schema secured by directive-based authentication enforcement.

**Endpoint:** N/A - library/tooling, no hosted endpoint. Each Redwood application serves its own GraphQL API at `/graphql` (configurable).

**Documentation:** https://docs.redwoodjs.com/docs/graphql

**References:**
- Documentation: https://docs.redwoodjs.com/docs/graphql
- Directives: https://docs.redwoodjs.com/docs/directives
- GitHub: https://github.com/redwoodjs/redwood/tree/main/packages/graphql-server
- Root Schema source: https://github.com/redwoodjs/redwood/blob/main/packages/graphql-server/src/rootSchema.ts
- GraphQL Yoga: https://the-guild.dev/graphql/yoga-server
- Envelop plugins: https://the-guild.dev/graphql/envelop
- GraphQL Armor: https://the-guild.dev/graphql/armor
