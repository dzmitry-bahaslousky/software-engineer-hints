`RETURNING` is an SQL clause used to return values from rows that have been affected by [[INSERT]], [[UPDATE]], or [[DELETE]] operations. It allows you to retrieve data that was altered by the operation without needing to perform a separate query.

## Key Functions of `RETURNING`

1. **Return Values**:
    - `RETURNING` allows you to retrieve the values of columns that were inserted or updated immediately after executing the command.
2. **Simplify Code**:
    - Using `RETURNING` eliminates the need for additional queries to obtain information about inserted or updated records, thus simplifying the code and reducing the number of database calls.
3. **Support for Various Data Types**:
    - You can return one or multiple columns, as well as computed values.

## Syntax

```sql
INSERT INTO table_name (column1, column2)
VALUES (value1, value2)
RETURNING column1, column2;

UPDATE table_name
SET column1 = new_value
WHERE condition
RETURNING column1, column2;

DELETE FROM table_name
WHERE condition
RETURNING column1, column2;
```