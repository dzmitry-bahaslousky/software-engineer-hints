The `BETWEEN` operator in SQL is used with [[WHERE]] to filter the result set within a specified range of values. It allows you to select rows where the column value falls between two given boundary values, inclusive of both the start and end values.

## How `BETWEEN` Works

**Inclusive Range**: The `BETWEEN` operator includes both the starting and ending values in the range.

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name BETWEEN value1 AND value2;
```

## Example Usage

**Numeric Range**:

```sql
SELECT * FROM orders WHERE total_amount BETWEEN 100 AND 500;
```

**Date Range**:

```
SELECT * FROM employees WHERE hire_date BETWEEN '2020-01-01' AND '2020-12-31';
```

**Textual Range**:

- **Query**: Select products with names that fall alphabetically between 'Apple' and 'Orange'.
```sql
SELECT * FROM products WHERE product_name BETWEEN 'Apple' AND 'Orange';
```

## Important Considerations

**Order of Values**: The lower boundary value should be placed first, followed by the higher boundary value. Reversing them will result in no rows being returned.

```sql
SELECT * FROM orders WHERE total_amount BETWEEN 500 AND 100; -- Incorrect, returns no rows
```

**NULL Values**: The `BETWEEN` operator does not return rows with `NULL` values in the specified column, as `NULL` is not considered within any range.