In **[[GraphQL]]**, a **Query** is used to fetch (or read) data from the server. It defines how clients can request specific data and is analogous to a GET request in REST APIs. Queries allow clients to specify exactly which fields of data they want, avoiding over-fetching or under-fetching information.  

### Key Features of a Query:

- **Flexible Data Retrieval**: Clients can request specific fields and relationships between objects.
- **Nested Data**: Queries can return related data in one request (e.g., a user and their posts).
- **Single Endpoint**: All queries are sent to the same endpoint, but the client defines the structure of the response.

### Example Query:

```graphql
{  
  user(id: "1") {  
    id  
    name  
    posts {  
      title  
    }  
  }  
}
```

### Response:

```graphql
{  
  "data": {  
    "user": {  
      "id": "1",  
      "name": "John Doe",  
      "posts": [  
        {  
          "title": "GraphQL Basics"  
        }  
      ]  
    }  
  }  
}
```

### Summary:

- **Query** is the mechanism to fetch data in GraphQL.
- Clients specify the fields they need, and the server returns just that data.