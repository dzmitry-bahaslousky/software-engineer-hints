**CREATE TABLE** is an SQL command used to create a new table in a database. This command is part of the **[[DDL|Data Definition Language]]** and allows you to define the structure of the table, including its columns, data types, and constraints.

## Key Elements of `CREATE TABLE`:

1. **Table Name**: Specified after `CREATE TABLE`, it defines the name of the table being created.
2. **Column Definitions**: For each column in the table, you specify a name, data type, and, if necessary, constraints.
3. **Constraints**: These are conditions imposed on the columns, such as `PRIMARY KEY`, `UNIQUE`, `NOT NULL`, and `FOREIGN KEY`.

### Example:
```sql
CREATE TABLE Employees (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    salary DECIMAL(10, 2),
    hire_date DATE,
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES Departments(id)
);
```

## Features of `CREATE TABLE`:

- **Data Structure Definition**: It defines the structure of the table that will be used to store data.
- **Automatic Commit**: Once the command is successfully executed, the table is created in the database, and the changes are automatically committed.
- **Constraints and Rules**: It allows you to set rules and constraints for the data that will be entered into the table.