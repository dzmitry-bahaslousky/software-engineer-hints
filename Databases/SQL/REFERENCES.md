The keyword in SQL is used to define a [[FOREIGN KEY]] constraint, specifying the relationship between two tables by indicating the parent table and the column(s) in that table that the foreign key in the child table references. It plays a crucial role in maintaining referential integrity within a relational database.

## How Works

- **Definition**: When creating a table with a foreign key, the `REFERENCES` clause indicates which table and column are referenced by the foreign key in the current table.

```sql
CREATE TABLE child_table (
    child_id INT PRIMARY KEY,
    parent_id INT,
    FOREIGN KEY (parent_id) REFERENCES parent_table(its_id)
);
```


## Important Characteristics

1. **Referential Integrity**: The `REFERENCES` keyword enforces referential integrity by ensuring that every foreign key value in the child table matches a valid primary key value in the parent table. This prevents the creation of orphan records in the child table.

2. **Cascading Actions**: When defining a foreign key using `REFERENCES`, you can also specify cascading actions such as `ON DELETE CASCADE` or `ON UPDATE CASCADE`. This means that if a record in the parent table is deleted or updated, the corresponding records in the child table can be automatically deleted or updated as well.

3. **Multiple References**: A table can have multiple foreign keys referencing different tables, allowing for complex relationships. Each `REFERENCES` clause can point to different parent tables and columns.

4. **Composite Foreign Keys**: If a foreign key consists of multiple columns, you can define it using the `REFERENCES` clause for a composite key, ensuring that the combination of values in the child table matches a combination of values in the parent table.