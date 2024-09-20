In **[[GraphQL]]**, a **schema** is the central component that defines the structure and types of data that can be queried or mutated through the API. It acts as the contract between the client and server, outlining what data is available, how it can be accessed, and the relationships between different data types.

### Key Concepts of GraphQL Schema:

1. **Types**:
    - The schema consists of types that define the shape of data. Common types include `Query`, `Mutation`, `Subscription`, and custom object types.

```graphql
type User {
  id: ID!
  name: String!
  age: Int
  posts: [Post]
}
```

2. **[[Query|Queries]]**:
	- Defines the read operations that clients can request.

```graphql
type Query {
  user(id: ID!): User
  allUsers: [User]
}
```

3. **[[Mutation|Mutations]]**:
	- Defines the write operations (like create, update, or delete) that modify server data.

```graphql
type Mutation {
  createUser(name: String!, age: Int): User
}
```

4. **Subscriptions**:
	- Defines real-time data operations that allow clients to receive updates when certain events occur.

```graphql
type Subscription {
  userUpdated: User
}
```

### How It Works:

- **Schema Definition Language (SDL)**: The schema is usually written using SDL, which defines the types, fields, and operations.
- **Strongly Typed**: Every field in the schema is associated with a specific type (e.g., `String`, `Int`, `User`), providing strong validation and tooling support.
- **Introspection**: Clients can query the schema itself to understand the available operations and data types.