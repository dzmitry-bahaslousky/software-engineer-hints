The `ON DELETE` clause in SQL is primarily used in the context of [[FOREIGN KEY]] constraints within table definitions. It specifies the action that should be taken when a record in the parent table (the table that holds the primary key) is deleted. This is crucial for maintaining referential integrity between tables. Here are the main options and their meanings:

### Key Functions of ON DELETE

1. **ON DELETE CASCADE**:
    
    - When a record in the parent table is deleted, all related records in the child table are also automatically deleted.
```sql
CREATE TABLE departments (
    department_id INT PRIMARY KEY,
    department_name VARCHAR(100)
);

CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id) ON DELETE CASCADE
);
```

2. **ON DELETE SET NULL**:
	
	- When a record in the parent table is deleted, the foreign key fields in the child table are set to `NULL`.
```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id) ON DELETE SET NULL);
```

3. **ON DELETE RESTRICT**:
	
	- This prevents the deletion of a record in the parent table if there are related records in the child table. It maintains referential integrity by disallowing the deletion.

```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id) ON DELETE RESTRICT);
```

4. **ON DELETE NO ACTION**:
	
	- Similar to `RESTRICT`, this option also prevents the deletion of a record in the parent table if related records exist in the child table. However, the check is performed after all constraints have been evaluated.
```sql
CREATE TABLE employees (
    employee_id INT PRIMARY KEY,
    employee_name VARCHAR(100),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES departments(department_id) ON DELETE NO ACTION);
```