**INSERT INTO** is an SQL command used to add new records (rows) into a table within a database. It is part of the **[[DML|Data Manipulation Language]]** subset of SQL, which focuses on manipulating the data stored in the database.
## Key Components of `INSERT INTO`:

1. **Table Name**: Specifies the table into which the data will be inserted.
2. **Column List** (optional): Specifies the columns in which you want to insert data. If you omit the column list, values must be provided for all columns in the table in the exact order they appear in the table definition.
3. **Values**: Specifies the actual data to be inserted into the specified columns.

## Examples:

```sql
INSERT INTO Employees (id, name, salary, hire_date, department_id)
VALUES (1, 'John Doe', 50000, '2023-09-01', 2);
```

### Simplified Example Without Column List:
```sql
INSERT INTO Employees 
VALUES (2, 'Jane Smith', 55000, '2023-09-15', 3);
```

### Example of Inserting Multiple Rows:
```sql
INSERT INTO Employees (id, name, salary, hire_date, department_id)
VALUES 
(3, 'Alice Johnson', 60000, '2023-09-20', 2),
(4, 'Bob Brown', 62000, '2023-09-22', 1);
```

## Features of `INSERT INTO`:

- **Adding Data**: The primary function of `INSERT INTO` is to add new rows of data to a table.
- **Single or Multiple Rows**: You can insert one row at a time or multiple rows in a single `INSERT INTO` statement by listing multiple sets of values.
- **Data Integrity**: The command must comply with any constraints on the table, such as `NOT NULL`, `UNIQUE`, `PRIMARY KEY`, or `FOREIGN KEY`.