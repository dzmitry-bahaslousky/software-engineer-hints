The `LIKE` operator in SQL is used with [[WHERE]] to search for a specified pattern in a column. It's particularly useful for performing partial matches in text data, allowing you to retrieve rows that fit a certain criteria even when only part of the data is known.

## How `LIKE` Works

The `LIKE` operator is typically used in a `WHERE` clause to filter rows based on a pattern match. It supports two primary wildcard characters:

- **`%`**: Represents zero or more characters. It can be used to match any sequence of characters (including an empty sequence).
- **`_`**: Represents a single character. It is used to match a specific character position.

## Basic Structure

```sql
SELECT column1, column2, ...
FROM table_name
WHERE column_name LIKE pattern;
```

## Case Sensitivity

The behavior of the `LIKE` operator regarding case sensitivity depends on the database system:

- **MySQL**: Case-insensitive by default for `LIKE` comparisons, unless the column's collation is case-sensitive.
- **PostgreSQL**: Case-sensitive by default, but you can use `ILIKE` for case-insensitive matches.
- **SQL Server**: Case sensitivity depends on the collation of the column.

## Advanced Usage with Escape Characters

Sometimes you need to match the actual `%` or `_` characters in your data. In such cases, SQL allows you to define an escape character:

```sql
SELECT * FROM table_name WHERE column_name LIKE '%\%%' ESCAPE '\';
```

**Explanation**: Here, the backslash `\` is defined as an escape character, so `\%` is treated as a literal percentage sign.