`GraphSemantic` is an enumeration in Hibernate that defines how an [[Entity Graphs]] should be applied in JPA (Java Persistence API). It offers two main modes:

- **`FETCH`**:
    - When the `EntityGraph` is interpreted as a "fetch graph":
        - Attributes explicitly specified in the graph (via `AttributeNode`) are treated as `FetchType.EAGER` and are fetched immediately, either through a join or an additional select query.
        - Attributes not specified in the graph are treated as `FetchType.LAZY` and are not fetched immediately.

- **`LOAD`**:
    - When the `EntityGraph` is interpreted as a "load graph":
        - Attributes explicitly specified in the graph are also treated as `FetchType.EAGER` and are fetched immediately.
        - However, attributes not specified in the graph are fetched according to their original fetching strategy (`FetchType.LAZY` or `FetchType.EAGER`) as defined in the entity's mapping.

## Usage Context:

This enumeration is used in Hibernate to control how entity graphs are applied when fetching data from the database. It allows developers to optimize performance by managing the loading strategy of associated entities.