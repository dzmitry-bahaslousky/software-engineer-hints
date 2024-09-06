A **RIGHT OUTER JOIN** (or simply **RIGHT JOIN**) retrieves all rows from the right table and the matching rows from the left table. If there is no match, the result will still include the rows from the right table, but the columns from the left table will contain `NULL`.

### Key Points:

1. **All Rows from the Right Table**: The result will include all rows from the right (second) table.
2. **Matching Rows from the Left Table**: For rows that have matching values in the left (first) table, those values are returned. If there is no match, `NULL` is returned for the columns from the left table.
3. **Retains Non-Matching Right Rows**: Even if there is no matching row in the left table, rows from the right table will still appear in the result set.

### Syntax

```sql
SELECT column_list
FROM table1
RIGHT JOIN table2
ON table1.column = table2.column;
```

### Use Cases:

- **Retain All Data from One Table**: `RIGHT JOIN` is useful when you want to include all records from the right table, even if some don’t have corresponding entries in the left table.
- **Handling Missing Relationships**: When some records in one table may not have corresponding records in another table, but you still want to include them in the result.

### Performance Considerations:

- **Efficiency**: Similar to `LEFT JOIN`, but it starts with the right table. Proper indexing on the columns used for the join is important to maintain performance.
- **NULL Values**: Like with `LEFT JOIN`, `NULL` values can complicate filtering and further data manipulation.