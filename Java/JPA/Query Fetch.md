**Query Fetch** (or **Fetch Join**) is a method used in JPA and Hibernate to load related entities in a single SQL query by using the `JOIN` operation. This approach helps avoid the N+1 query problem and improves performance when retrieving data from the database.

## Key Features of Query Fetch:

1. **Single Query**:
   Instead of executing multiple queries to load the main entity and its associated data, `Fetch Join` allows you to retrieve all necessary data in a single query. For example, you can load a `User` entity and its associated `Orders` with one SQL query.

2. **Avoids the [[N + 1]] Problem**:
   When using lazy loading, the N+1 query problem can occur, where one query is executed to load the main entity, and then separate queries are executed for each related entity. `Fetch Join` prevents this by combining everything into one query.

3. **Pagination Issues**:
   It's important to note that using `Fetch Join` can complicate pagination because the resulting data set may include duplicates of the main entity due to multiple associated records.

Example:
```JPQL
SELECT u FROM User u JOIN FETCH u.orders
```
