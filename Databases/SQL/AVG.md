The `AVG` function in SQL is an aggregate function that calculates the average value of a numeric column in a table. It is commonly used in conjunction with the [[SELECT]] statement to derive meaningful insights from data.

## Syntax

```sql
SELECT AVG(salary) AS average_salary
FROM employees;
```

### How `AVG` Works

- **Calculation**: The `AVG` function sums up all the values in the specified column and divides this sum by the count of non-null entries in that column. This means that any `NULL` values in the column are ignored in the calculation.
## Important Notes

1. **Ignoring NULL Values**: The `AVG` function does not consider `NULL` values when performing the calculation. If all values in the column are `NULL`, the function will return `NULL`.

2. **Use in Grouping**: The `AVG` function can also be used with the `GROUP BY` clause to calculate averages for different groups of data. For instance, if you want to find the average salary by department, you can write:

```sql
SELECT department, AVG(salary) AS average_salary
FROM employees
GROUP BY department;
```

3. **Performance**: Like other aggregate functions, `AVG` can have performance implications on large datasets, especially if indexes are not utilized effectively.