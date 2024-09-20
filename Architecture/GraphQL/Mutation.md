In **[[GraphQL]]**, a **Mutation** is used to modify (create, update, or delete) data on the server. While **queries** are used to read data, **mutations** allow clients to perform write operations. Each mutation operation typically alters the server's state and can also return data, similar to how a query does.

### Key Features of a Mutation:

- **Modifies Data**: Used to create, update, or delete records.
- **Returns Data**: Mutations can return data after performing the operation, allowing clients to immediately see the results.
- **Similar to POST/PUT/DELETE in REST**: Mutations are analogous to actions that modify data in REST APIs.

### Example Mutation:

```graphql
mutation {  
  createUser(name: "Alice", age: 30) {  
    id  
    name  
    age  
  }  
}
```

### Response:

```graphql
{  
  "data": {  
    "createUser": {  
      "id": "1",  
      "name": "Alice",  
      "age": 30  
    }  
  }  
}
```

### Summary:

- **Mutation** in GraphQL is used to perform data modification (create, update, delete).
- Mutations can return the updated data after performing the operation.