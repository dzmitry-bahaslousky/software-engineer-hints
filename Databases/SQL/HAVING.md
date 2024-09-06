### How `HAVING` Works

`HAVING` is an SQL operator used to filter the results obtained from a [[GROUP BY]] clause. It allows you to specify conditions for aggregated data, making it useful for filtering groups after they have been created. This is different from the [[WHERE]] clause, which filters rows before aggregation.

### Key Points:

1. **Filtering Aggregated Data**: `HAVING` allows conditions to be applied to the results of aggregate functions, such as `SUM`, `COUNT`, `AVG`, etc.
2. **Used with `GROUP BY`**: It is typically used in conjunction with `GROUP BY` to filter the results of the groups.
3. **Execution Order**: SQL first performs the grouping of data, then applies the `HAVING` conditions.

### Syntax

```sql
SELECT column1, aggregate_function(column2)
FROM table
WHERE condition
GROUP BY column1
HAVING condition_for_aggregate;
```

### Execution Process:

1. **Data Selection**: SQL first selects rows from the table, applying any `WHERE` conditions (if present).
2. **Grouping**: Rows are then grouped by the specified column (`product_name`).
3. **Applying Aggregate Functions**: Aggregate functions (e.g., `SUM`) are applied to each group.
4. **Filtering Results**: After grouping and applying aggregate functions, `HAVING` is applied to the results to return only those groups that satisfy the specified condition.