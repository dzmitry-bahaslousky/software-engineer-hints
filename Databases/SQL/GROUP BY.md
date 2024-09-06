`GROUP BY` is a SQL operator used to group rows that have the same values in specified columns. It is often used in conjunction with aggregate functions (such as [[SUM]], [[COUNT]], [[AVG]], [[MAX]], [[MIN]]) to perform calculations at the group level rather than on individual rows.

### Key Points:

1. **Grouping Rows**: `GROUP BY` combines rows with identical values in the specified columns into a single result row.
2. **Aggregate Functions**: It is commonly used with aggregate functions to summarize information for each group.
3. **Execution Order**: SQL executes `GROUP BY` after `FROM` and `WHERE` but before `ORDER BY`.

### Syntax

```sql
SELECT column1, aggregate_function(column2)
FROM table
WHERE condition
GROUP BY column1;
```

### Execution Process:

1. **Data Selection**: First, rows are selected from the table, applying any `WHERE` conditions (if present).
2. **Grouping**: Rows are then grouped by the specified column (`product_name`).
3. **Applying Aggregate Functions**: Aggregate functions (e.g., `SUM`) are applied to each group.
4. **Result Formation**: The final result is returned as a table with aggregated data.