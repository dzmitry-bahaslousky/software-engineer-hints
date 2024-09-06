A **subquery** in SQL is a query nested inside another SQL query. It can be used in various parts of a SQL statement, such as in the [[SELECT]], `FROM`, or [[WHERE]] clauses. Subqueries help break down complex queries into simpler parts, making them easier to read and maintain.
## Uses of Subqueries

- **Filtering Results**: Subqueries can be used in the `WHERE` clause to filter records based on conditions derived from another query.
- **Calculating Values**: They can be used in the `SELECT` clause to calculate values based on other tables.
- **Joining Data**: Subqueries can act as temporary tables within the `FROM` clause.

## Where to use

### 1. **In the SELECT Clause**

- Subqueries can be used to calculate values or retrieve additional data for each row in the result set.
```sql
SELECT employee_name,
       (SELECT COUNT(*) FROM projects WHERE projects.employee_id = employees.id) AS project_count
FROM employees;
```

### 2. **In the WHERE Clause**

- Subqueries can filter records based on conditions derived from another query.
```sql
SELECT employee_name 
FROM employees 
WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'Sales');
```

### 3. **In the FROM Clause**

- Subqueries can act as derived tables, allowing you to join or select from them like a regular table.
```sql
SELECT avg_salary.department_id, avg_salary.average_salary
FROM (SELECT department_id, AVG(salary) AS average_salary
      FROM employees
      GROUP BY department_id) AS avg_salary;
```

### 4. **In the HAVING Clause**

- Subqueries can filter aggregated results based on conditions from another query.
```sql
SELECT department_id, COUNT(*) AS employee_count
FROM employees
GROUP BY department_id
HAVING COUNT(*) > (SELECT AVG(employee_count) FROM (SELECT COUNT(*) AS employee_count FROM employees GROUP BY department_id) AS dept_counts);
```

### 5. **In the INSERT Statement**

- Subqueries can be used to insert data into a table based on data from another table.
```sql
INSERT INTO new_employees (employee_name, department_id)
SELECT employee_name, department_id 
FROM employees 
WHERE salary > (SELECT AVG(salary) FROM employees);
```

### 6. **In the UPDATE Statement**

- Subqueries can modify data in one table based on conditions derived from another table.
```sql
UPDATE employees 
SET department_id = (SELECT id FROM departments WHERE department_name = 'Marketing') 
WHERE salary > (SELECT AVG(salary) FROM employees);
```

### 7. **In the DELETE Statement**

- Subqueries can be used to delete records from a table based on conditions derived from another table.
```sql
DELETE FROM employees 
WHERE department_id IN (SELECT id FROM departments WHERE location_id = 100);
```

## Benefits

- **Modularity**: Breaking down complex SQL statements into simpler components.
- **Clarity**: Improving readability by isolating parts of the query logic.
- **Reusability**: Allowing the use of the same query logic multiple times within a larger query.

## Limitations

- Performance may be affected in certain situations, especially with correlated subqueries, as they may execute multiple times for each row in the outer query.
- Complexity can increase if overused, making the overall query harder to understand.