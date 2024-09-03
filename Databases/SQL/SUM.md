The `SUM` function in SQL is used with [[SELECT]] to calculate the total sum of a numeric column in a table. It adds up all the values in a specified column and returns the result. This function is commonly used in data analysis to find totals or aggregate data within a dataset.

## Syntax

```sql
SELECT SUM(column_name)
FROM table_name
WHERE condition;
```

### Key Points

- **Numeric Columns:** The `SUM` function only works on columns with numeric data types, such as integers, floats, or decimals.

- **NULL Values:** The `SUM` function ignores `NULL` values in the column. It only adds up the non-null values.

- **Grouping Data:** The `SUM` function can be combined with the `GROUP BY` clause to calculate sums for specific groups of data.
```sql
SELECT customer_id, SUM(amount) AS total_sales
FROM sales
GROUP BY customer_id;
```

## Limitations

- **Non-Numeric Columns:** The `SUM` function cannot be used on columns with non-numeric data types, like strings or dates.

- **Large Datasets:** Calculating the sum on very large datasets can be resource-intensive and might affect performance.