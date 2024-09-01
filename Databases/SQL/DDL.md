**DDL** (Data Definition Language) is a subset of **SQL** (Structured Query Language) used to define, manage, and manipulate database structures. DDL commands are primarily used to create, modify, and delete database objects such as tables, indexes, schemas, and views.
## Key DDL Commands:

1. **CREATE**: Used to create new database objects.

```sql
CREATE TABLE Employees (
    id INT PRIMARY KEY,
    name VARCHAR(100),
    salary DECIMAL(10, 2)
);
```

2. **ALTER**: Used to modify existing database objects.

```sql
ALTER TABLE Employees ADD COLUMN hire_date DATE;
```

3. **DROP**: Used to delete database objects.

```sql
DROP TABLE Employees;
```

## DDL Characteristics:

- **Implicit Commit**: Unlike **[[DML]]** (Data Manipulation Language) commands, **DDL** commands automatically commit changes, meaning they do not require an explicit `COMMIT` statement. The changes made by **DDL** commands are immediately and permanently applied to the database.
- **Structural Modifications**: **DDL** commands are used to define or alter the structure of database objects, as opposed to **[[DML]]** commands, which manage the data within those structures.