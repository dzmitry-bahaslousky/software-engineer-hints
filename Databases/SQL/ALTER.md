The **`ALTER`** command in SQL is used to modify the structure of existing database objects, such as tables, views, indexes, and others. It allows changes to be made to already created objects without the need to delete and recreate them.

### Main operations with `ALTER`:

1. **Modifying a table**:
    
    - **Adding a column**:
        
        ALTER TABLE table_name ADD column_name data_type;
        
    - **Dropping a column**:
        
        `ALTER TABLE table_name DROP COLUMN column_name;`
        
    - **Changing a column's data type**:
        
        `ALTER TABLE table_name MODIFY column_name new_data_type;`
        
2. **Renaming a table**:
    
    `ALTER TABLE old_table_name RENAME TO new_table_name;`
    
3. **Adding or changing constraints**:
    
    - **Adding a constraint**:
        
        `ALTER TABLE table_name ADD CONSTRAINT constraint_name UNIQUE (column_name);`
        
    - **Dropping a constraint**:
        
        `ALTER TABLE table_name DROP CONSTRAINT constraint_name;`