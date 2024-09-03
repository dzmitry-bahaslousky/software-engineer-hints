The `MIN` function in SQL is an aggregate function that returns the smallest value from a specified column in a table. It is commonly used with [[SELECT]] in data analysis and reporting to determine the lowest value within a dataset.

## How `MIN` Works

- **Calculation**: The `MIN` function scans the specified column and retrieves the lowest value found. Any `NULL` values in the column are ignored in the calculation.

#### Important Notes

1. **Ignoring NULL Values**: The `MIN` function does not consider `NULL` values when determining the minimum. If all values in the column are `NULL`, the function will return `NULL`.

2. **Use in Grouping**: The `MIN` function can also be used with the `GROUP BY` clause to find minimum values for different groups of data. For example, if you want to find the minimum price of products by category, you can write:

```sql
SELECT category, MIN(price) AS minimum_price
FROM products
GROUP BY category;
```

3. **Performance**: Like other aggregate functions, `MIN` can have performance implications on large datasets, especially if appropriate indexes are not in place.