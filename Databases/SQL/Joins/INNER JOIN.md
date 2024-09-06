An **INNER JOIN** is a type of SQL join that retrieves only the rows that have matching values in both tables based on a specified condition. If there are no matching rows in one of the tables, those rows are excluded from the result set. This join returns the intersection of the two tables, where the join condition is met.

### Key Points:

1. **Matching Rows Only**: It only includes rows from both tables where the specified condition is true (i.e., where a match exists in both tables).
2. **Commonly Used for Relational Data**: Often used when you want to combine data that is directly related through [[FOREIGN KEY]] or other relationships.

### How It Works:

1. **Define the Tables**: You select data from two (or more) tables.
2. **Specify the Join Condition**: The condition is typically a comparison between a column in one table and a column in another (often a foreign key-primary key relationship).
3. **Return Matching Rows**: SQL returns only the rows where the condition evaluates to true, ignoring rows without matches in either table.

```sql
SELECT column_list
FROM table1
INNER JOIN table2
ON table1.column = table2.column;
```

### Use Cases:

- **Relational Queries**: Used when you need to combine related data from two or more tables, such as retrieving customer information with their orders.
- **Database Normalization**: Helps query normalized databases where data is split across multiple tables to avoid redundancy.

### Performance Considerations:

- **Efficiency**: `INNER JOIN` is usually efficient when both tables have indexes on the columns used in the join condition.
- **Large Datasets**: On large datasets, performance might degrade if proper indexing is not used, so it's crucial to ensure the joined columns are indexed.

