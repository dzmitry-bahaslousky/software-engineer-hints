**Constraints** are rules enforced on data columns in a table to ensure the integrity, accuracy, and reliability of the data. They define the conditions that data must meet to be accepted into the database.
## Key Types of Constraints:

1. **PRIMARY KEY**:
	- Ensures that each row in a table is unique.
	- Does not allow `NULL` values and prevents duplicate entries.
```sql
CREATE TABLE Employees (
    id INT PRIMARY KEY,
    name VARCHAR(100)
);
```

2. **[[FOREIGN KEY]]**:
	- Enforces referential integrity between two tables.
	- The value in the foreign key column must match a value in the primary key column of another table or be `NULL`.
```sql
CREATE TABLE Orders (
    order_id INT PRIMARY KEY,
    customer_id INT,
    FOREIGN KEY (customer_id) REFERENCES Customers(id)
);
```

3. **[[UNIQUE]]**:
	- Ensures all values in a column or a group of columns are unique.
	- Allows `NULL` values, but each `NULL` must be unique.
```sql
CREATE TABLE Employees (
    id INT,
    email VARCHAR(100) UNIQUE
);
```

4. **NOT NULL**:
	- Ensures that a column cannot have a `NULL` value.
```sql
CREATE TABLE Employees (
    id INT,
    name VARCHAR(100) NOT NULL
);
```

5. **CHECK**:
	- Defines a condition that must be met for data in a column.
```sql
CREATE TABLE Employees (
    id INT,
    age INT,
    CHECK (age >= 18)
);
```

6. **DEFAULT**
	- Sets a default value for a column when no value is specified during insertion.
```sql
CREATE TABLE Employees (
    id INT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

## Example with Multiple Constraints:

```sql
CREATE TABLE Employees (
    id INT PRIMARY KEY,
    name VARCHAR(100) NOT NULL,
    email VARCHAR(100) UNIQUE,
    age INT CHECK (age >= 18),
    department_id INT,
    FOREIGN KEY (department_id) REFERENCES Departments(id)
);
```