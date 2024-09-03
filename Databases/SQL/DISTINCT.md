The `DISTINCT` keyword in SQL is used with [[SELECT]] to remove duplicate rows from the result set of a query. When you want to retrieve unique values from a column (or a combination of columns) in a table, you can use `DISTINCT` to ensure that the returned results contain only distinct values.

## Syntax
```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

## Use Cases

- **Data Analysis:** When analyzing data, you may want to know how many unique values exist in a column.
- **Reporting:** Generating reports that require unique entries, such as a list of unique customer names or product categories.
- **Data Cleaning:** Identifying and removing duplicate entries from a dataset.

## Performance Considerations

- **Resource Intensive:** Using `DISTINCT` can be resource-intensive, especially on large datasets, as the database must examine all rows to identify duplicates.
- **Indexing:** If the columns being queried are indexed, performance may be improved, as the database can more quickly identify unique values.