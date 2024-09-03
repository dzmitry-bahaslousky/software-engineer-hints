The `SELECT` statement is one of the most fundamental and widely used commands in SQL (Structured Query Language) and [[DML]]. It allows users to retrieve data from one or more tables in a database. The `SELECT` statement is the cornerstone of SQL queries and provides powerful ways to filter, sort, and format the data that is returned.

## Basic Structure of a `SELECT` Statement

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition
GROUP BY column_name(s)
HAVING condition
ORDER BY column_name(s) [ASC|DESC]
LIMIT number;
```

## Components of the `SELECT` Statement

**SELECT Clause**:
- The `SELECT` clause specifies the columns you want to retrieve from the database. You can select specific columns or use `*` to select all columns.
```sql
SELECT first_name, last_name FROM employees;
```

**FROM Clause**:
- The `FROM` clause specifies the table from which to retrieve the data.
```sql
SELECT first_name, last_name FROM employees;
```

**[[WHERE]] Clause**:
- The `WHERE` clause filters the records returned by the query based on specified conditions. Only rows that meet the condition(s) are returned.
```sql
SELECT first_name, last_name FROM employees WHERE department = 'Sales';
```

**[[GROUP BY]] Clause**:
- The `GROUP BY` clause groups rows that have the same values in specified columns into summary rows, like "total sales by department."
- It is often used with aggregate functions like `COUNT()`, `SUM()`, `AVG()`, `MAX()`, `MIN()`.
```sql
SELECT department, COUNT(*) FROM employees GROUP BY department;
```

**HAVING Clause**:
- The `HAVING` clause is similar to `WHERE` but is used to filter groups after aggregation, particularly when you use `GROUP BY`.
```sql
SELECT department, COUNT(*) 
FROM employees 
GROUP BY department 
HAVING COUNT(*) > 10;
```

**[[ORDER BY]] Clause**:
- The `ORDER BY` clause sorts the result set by one or more columns. You can specify ascending (`ASC`) or descending (`DESC`) order.
```sql
SELECT first_name, last_name FROM employees ORDER BY last_name ASC;
```

**[[LIMIT]] Clause**:
- The `LIMIT` clause restricts the number of rows returned by the query. This is useful when you want to get just a subset of the records.
```sql
SELECT first_name, last_name FROM employees ORDER BY last_name ASC LIMIT 10;
```

## Additional Features

**Aliasing (`AS`)**:
- You can use the `AS` keyword to assign a temporary name to a column or table within the query.
```sql
SELECT first_name AS "First Name", last_name AS "Last Name" FROM employees;
```

**Joins**:
- `SELECT` statements often involve joining multiple tables to combine related data. Common types of joins include `INNER JOIN`, `LEFT JOIN`, `RIGHT JOIN`, and `FULL JOIN`.
```sql
SELECT employees.first_name, employees.last_name, departments.department_name
FROM employees
INNER JOIN departments ON employees.department_id = departments.department_id;
```

**Subqueries**:
- A subquery is a query nested inside another query. Subqueries can be used in various places, such as the `SELECT`, `FROM`, and `WHERE` clauses.
```sql
SELECT first_name, last_name 
FROM employees 
WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'Sales');
```