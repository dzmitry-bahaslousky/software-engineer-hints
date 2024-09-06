A **LEFT OUTER JOIN** (commonly referred to simply as **LEFT JOIN**) returns all the rows from the left table and the matching rows from the right table. If there is no match, the result will still include the rows from the left table, but the columns from the right table will contain `NULL`.

### Key Points:

1. **All Rows from Left Table**: The result includes all rows from the left (first) table.
2. **Matching Rows from Right Table**: For rows that have matching values in the right (second) table, those values are returned. If there is no match, `NULL` is returned for the columns of the right table.
3. **Retains Non-Matching Left Rows**: Even if there is no matching row in the right table, rows from the left table will still appear in the result set.

### Syntax

```sql
SELECT column_list
FROM table1
LEFT JOIN table2
ON table1.column = table2.column;
```

### Use Cases:

- **Retain All Data from One Table**: You want to include all records from the left table, even if some don’t have corresponding entries in the right table.
- **Handling Missing Relationships**: When some records in one table may not have corresponding records in another table, but you still want to include them in the output (with `NULL` where there’s no match).

### Performance Considerations:

- **Efficiency**: `LEFT JOIN` can perform efficiently with proper indexing on the columns used for joining.
- **NULL Values**: Be aware that `NULL` values may complicate further data processing or filtering in your query results.