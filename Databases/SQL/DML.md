**DML** (Data Manipulation Language) is a subset of SQL (Structured Query Language) that is used for managing and manipulating data within database objects, such as tables. DML commands allow users to perform operations that add, update, delete, or retrieve data from the database.

## Key DML Commands:

1. **[[INSERT]]**: Used to add new records to a table.

```sql
INSERT INTO Employees (id, name, salary) 
VALUES (1, 'John Doe', 50000);
```

2. **[[UPDATE]]**: Used to modify existing records in a table.

```sql
UPDATE Employees 
SET salary = 55000 
WHERE id = 1;
```

3. **[[DELETE]]**: Used to remove records from a table.

```sql
DELETE FROM Employees 
WHERE id = 1;
```

4. **[[SELECT]]**: Used to retrieve data from one or more tables.

```sql
SELECT * FROM Employees;
```

## Characteristics of DML:

- **Data Focused**: **DML** commands focus on the manipulation of data stored within the database, as opposed to **[[DDL]]** commands, which focus on the structure of the database itself.
- **Transaction Control**: **DML** operations are often part of transactions, which can be committed or rolled back, allowing for more controlled data management. This means that if an operation fails, changes can be undone to maintain data integrity.