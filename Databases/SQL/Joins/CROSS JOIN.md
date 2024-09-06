A **CROSS JOIN** returns the [[Cartesian product]] of two tables, meaning it combines every row from the first table with every row from the second table. This type of join does not require a join condition (unlike [[INNER JOIN]] or `LEFT JOIN`) and will return all possible combinations of rows between the two tables.

### Key Points:

1. **No Condition Required**: Unlike other types of joins, `CROSS JOIN` does not require a condition to match rows from the two tables.
2. **Cartesian Product**: The result of a `CROSS JOIN` is the Cartesian product, where the number of rows in the result set is the product of the number of rows in both tables.
    - If Table 1 has 5 rows and Table 2 has 3 rows, the result of the `CROSS JOIN` will have 5×3=15  rows.

### Syntax:

```sql
SELECT column_list
FROM table1
CROSS JOIN table2;
```

### How It Works:

1. **No Matching Criteria**: `CROSS JOIN` doesn’t filter rows based on a condition. It simply combines every row from the first table with every row from the second table.
2. **Result Size**: If `table1` has **m** rows and `table2` has **n** rows, the result set will contain **m × n** rows.

### Use Cases:

- **Cartesian Product Scenarios**: `CROSS JOIN` can be useful in scenarios where you need every possible combination of rows between two tables, for example, to generate test data or explore combinations.
- **Multiplying Data**: It can be used when multiplying one set of data by another set to analyze all possible combinations.

### Caution:

- **Large Datasets**: Be careful when using `CROSS JOIN` on large datasets because the result set can grow exponentially. For example, joining a table with 1,000 rows and another with 1,000 rows will produce 1,000,000 rows in the result.
- **Performance**: Since it doesn’t use a join condition, it’s computationally expensive if used on large tables without filters.

### Difference from Other Joins:

- **INNER JOIN**: Returns only matching rows between tables based on a condition.
- **LEFT/RIGHT JOIN**: Returns all rows from one table and the matching rows from the other.
- **CROSS JOIN**: Returns all possible combinations of rows between tables, with no regard for matching conditions.