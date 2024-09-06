The `UPDATE` statement in SQL is used to modify existing records in a database table. It allows you to change one or more columns for one or more rows in a table. Here are the key aspects of what the `UPDATE` statement is responsible for:

## Syntax

```sql
UPDATE employees
SET salary = 50000
WHERE employee_id = 1;
```

**Modifying Data**:

- The `UPDATE` statement allows you to change the values in one or more columns of existing records.

**Updating Multiple Columns**:

- You can update multiple columns simultaneously.

**Conditional Updates**:

- The update can be applied to specific records using the `WHERE` clause. If no condition is specified, all records in the table will be updated.

**Using Subqueries**:

- `UPDATE` can also use subqueries to determine new values.

**Updating with JOIN**:

- You can update records using a `JOIN` to connect with other tables.
```sql
UPDATE employees e
JOIN departments d ON e.department_id = d.department_id
SET e.salary = e.salary * 1.1
WHERE d.department_name = 'Sales';
```