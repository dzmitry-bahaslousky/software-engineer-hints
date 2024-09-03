The **UNION** operator in SQL is used to combine the result sets of two or more [[SELECT]] statements into a single result set. It is an essential tool for querying multiple tables or datasets where the structure (i.e., the number and types of columns) is the same.

## Syntax

```sql
SELECT column1, column2 FROM table1
UNION
SELECT column1, column2 FROM table2;
```

## Key Characteristics

1. **Distinct Rows**: The result set of a `UNION` operation contains only distinct rows. If there are duplicate rows between the results of the combined `SELECT` statements, only one instance of each duplicate row will appear in the final output.

2. **Same Number of Columns**: All `SELECT` statements combined using `UNION` must have the same number of columns. Each `SELECT` statement must also have corresponding columns with compatible data types (e.g., both should be `INTEGER`, `VARCHAR`, etc.).

3. **Order of Columns**: The order of the columns in the `SELECT` statements must match. The first column of the first query will be combined with the first column of the second query, and so on.

## Variants of UNION

**UNION ALL**: Unlike `UNION`, the `UNION ALL` operator includes all duplicates in the result set. It combines the results of the `SELECT` statements without removing duplicate rows:

```sql
SELECT column1 FROM table1
UNION ALL
SELECT column1 FROM table2;
```

## Important Considerations

1. **Performance**: `UNION` can be slower than `UNION ALL` because it has to remove duplicates. If you know there will be no duplicates or if you want all records, use `UNION ALL` for better performance.

2. **Sorting Results**: If you want to order the final result set, you can use the `ORDER BY` clause at the end of the entire `UNION` query:

```sql
SELECT name FROM employees
UNION
SELECT name FROM contractors
ORDER BY name;
```

3. **Column Aliases**: If you want to provide a name for the columns in the result set, you can do so by using aliases in the first `SELECT` statement. The aliases will apply to the entire result set.

