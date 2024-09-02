Specifies the default fetching method for the annotated association. When this annotation is not explicitly specified, then:
- select fetching is used for lazy fetching, and
- join fetching is used for eager fetching.

The default fetching method specified by this annotation may be overridden in a given [[@FetchProfile]].

This annotation accept FetchMode.

## Description of `FetchMode`:

1. **SELECT**:

- **Description**: This mode uses a separate `SELECT` statement to load related entities or collections after the initial query is executed. This is the default fetching strategy for any association or collection in Hibernate unless it's explicitly marked for eager fetching (`FetchType.EAGER`).
- **Features**:
    - Vulnerable to the "[[N + 1]] selects" problem, where a separate query is executed for each related entity.
    - This issue can be mitigated by enabling batch fetching using the **[[@BatchSize]]** annotation or utilizing the second-level cache.
    - Compatible with both eager (`FetchType.EAGER`) and lazy (`FetchType.LAZY`) fetching.

2. **JOIN**:

- **Description**: This mode uses an `OUTER JOIN` to load all instances of the related entity or collection at once as part of the execution of the initial query. No subsequent queries are executed.
- **Features**:
    - It is the default fetching strategy for associations or collections explicitly marked as `FetchType.EAGER`.
    - Incompatible with lazy fetching (`FetchType.LAZY`), as the associated data is retrieved with the initial query.

3. **SUBSELECT**:

- **Description**: This mode uses a secondary `SELECT` with a subselect that re-executes the initial query to load all instances of the related entity or collection at once. This strategy is currently **only available for collections and many-valued associations**.
- **Features**:
    - Compatible with both eager (`FetchType.EAGER`) and lazy (`FetchType.LAZY`) fetching.
    - Unlike batch fetching, where a list of primary key values is sent to the database in an `IN` clause, subselect fetching determines the primary keys by re-executing the initial query within a SQL subselect.