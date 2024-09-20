**GraphQL** is a query language for APIs and a runtime for executing those queries by allowing clients to request only the data they need. It was developed by Facebook in 2012 and open-sourced in 2015. Unlike traditional REST APIs, which expose multiple endpoints for different resources, GraphQL provides a more flexible and efficient way to interact with APIs by allowing the client to define the structure of the response.

### Key Features of GraphQL:

1. **Single Endpoint**:
    
    - In GraphQL, you interact with a single endpoint (`/graphql`), where clients can specify exactly what data they need, rather than having multiple endpoints as in REST.
2. **Flexible Queries**:
    
    - Clients can request only the specific fields they need, which reduces over-fetching (getting unnecessary data) and under-fetching (missing required data).
3. **Strongly Typed Schema**:
    
    - GraphQL uses a strongly typed schema to define the shape and structure of the API. This allows for better tooling, validation, and introspection (querying the API about its own structure).
4. **Hierarchical Data**:
    
    - GraphQL queries mirror the structure of the returned data. Clients can request related data (nested queries) in one request, reducing the need for multiple round-trips to the server.
5. **Real-Time with Subscriptions**:
    
    - GraphQL supports real-time updates through **subscriptions**, allowing clients to receive data whenever it changes on the server.
6. **Client-Driven API**:
    
    - Clients have more control over the data they receive. They can combine multiple resources into one request, simplifying interactions with complex APIs.

### Example of GraphQL Query:

Here’s a simple GraphQL query:
```graphql
{
  user(id: "1") {
    name
    age
    posts {
      title
      content
    }
  }
}
```

In this query, the client is requesting the `name`, `age`, and related `posts` (with `title` and `content`) for the user with `id = 1`. The server responds with exactly that data, and nothing more.

### Comparison to REST:

- **REST**: Multiple endpoints, predefined responses, over-fetching/under-fetching common.
- **GraphQL**: Single endpoint, flexible queries, client defines the structure of the response.

### Benefits of GraphQL:

- **Efficiency**: Avoids over-fetching and under-fetching by allowing clients to request specific data.
- **Flexibility**: Clients can query multiple resources in a single request.
- **Evolvability**: Allows APIs to evolve over time without breaking clients by adding new fields and deprecating old ones.
- **Tooling**: Strongly typed schema enables auto-generated documentation, better error handling, and introspection.

### Use Cases:

- Ideal for complex systems with many relationships between entities.
- Helpful in mobile or low-bandwidth environments, where minimizing data transfer is crucial.
- Real-time applications with frequent updates using subscriptions.

In summary, GraphQL offers a more flexible and efficient approach to API design by allowing clients to query exactly the data they need from a single endpoint, making it a powerful alternative to REST.