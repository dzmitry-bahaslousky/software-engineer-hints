It is a constraint used in relational database management systems (RDBMS) to create a link between two tables. It ensures that the values in one table correspond to values in another table, thereby maintaining data integrity and enforcing relationships between the tables.

## How Works

- **Definition**: A foreign key in a table points to a primary key in another table. This establishes a parent-child relationship between the two tables, where the child table contains the foreign key and the parent table contains the primary key.

```sql
CREATE TABLE child_table (
    child_id INT PRIMARY KEY,
    parent_id INT,
    FOREIGN KEY (parent_id) REFERENCES parent_table(parent_id)
);
```

## Important Characteristics

1. **Referential Integrity**: The foreign key ensures that relationships between tables remain consistent. For example, if an employee references a department, that department must exist in the `departments` table.

2. **Cascading Actions**: Foreign keys can have cascading actions associated with them. For example, you can specify that if a referenced row in the parent table is deleted, all corresponding rows in the child table should also be deleted (CASCADE) or set to `NULL` (SET NULL).

3. **Multiple Foreign Keys**: A table can have multiple foreign keys referencing different tables, allowing complex relationships between multiple entities.

4. **Composite Foreign Keys**: You can create a foreign key that consists of multiple columns. This is known as a composite foreign key and requires the corresponding primary key in the referenced table to also be a composite key.