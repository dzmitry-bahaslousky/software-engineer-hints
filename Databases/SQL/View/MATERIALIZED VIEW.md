A **Materialized View** is a database object that stores the result of a query physically. Unlike a regular [[VIEW]], which is a virtual table that generates data on-the-fly, a materialized view saves the data on disk. This allows for significantly faster query execution, especially in cases where data does not change frequently and is primarily read.

### Key Points:

1. **Physical Storage**: The data in a materialized view is stored on disk, enabling quicker access.
2. **Refresh Mechanism**: Materialized views may require periodic refreshing to remain up-to-date. This can be done manually or automatically at specified intervals.
3. **Performance Improvement**: Using materialized views can greatly enhance the performance of complex queries and reports, as they eliminate the need for repeated calculations.
4. **Indexes**: Indexes can be created on materialized views, further speeding up query execution.

### Syntax

```sql
CREATE MATERIALIZED VIEW view_name AS
SELECT column1, column2
FROM table_name
WHERE condition;
```

#### Refreshing a Materialized View:

To update the data in a materialized view, you can use:
```sql
REFRESH MATERIALIZED VIEW TotalSales;
```

### Supported DB

Not all database management systems (DBMS) support materialized views, but many popular ones do. Here are some common DBMS that support materialized views:

1. **Oracle Database**: Supports materialized views with extensive features, including refresh options and partitioning.
2. **PostgreSQL**: Supports materialized views, allowing users to create and refresh them, although some features like automatic refresh are not available by default.
3. **Microsoft SQL Server**: Supports indexed views, which function similarly to materialized views but have some limitations in terms of complexity.
4. **MySQL**: Does not have built-in support for materialized views, but you can simulate them using regular tables and triggers or scheduled jobs.
5. **IBM Db2**: Supports materialized query tables, which are similar to materialized views.
6. **MariaDB**: As a fork of MySQL, it does not have native materialized view support, but users can implement similar functionality using other methods.
