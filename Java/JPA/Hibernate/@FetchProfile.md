The `FetchProfile` annotation defines a fetch profile by specifying its name and a list of fetch strategy overrides for associations. Fetch profiles enable fine-tuning of the data loading process by defining how related entities are retrieved from the database. This helps with [[N + 1]] problem.

## Key Features:

- A fetch profile can be defined across multiple `FetchProfile` annotations that share the same name.
- Fetch profiles allow specifying different fetch strategies for associations through the nested `FetchOverride` annotation.

## **Activation**:

- A named fetch profile must be explicitly enabled in a given session using the `Session.enableFetchProfile(String)` method for it to take effect at runtime.

## **Comparison with [[Entity Graphs]]**:

- Fetch profiles provide a list of fetch strategies, whereas JPA-defined `NamedEntityGraph` explicitly specifies paths to be fetched. Fetch profiles are determined recursively based on the root entity context.

## Annotation Components

- **FetchProfile Annotation**:
    - `name`: Specifies the unique name of the fetch profile within a persistence unit.
    - `fetchOverrides`: An array of `FetchOverride` annotations that define specific fetch strategy overrides for associations.

- **FetchOverride Annotation** (Nested within `FetchProfile`):
    - `entity`: Specifies the entity containing the association whose fetch strategy is being overridden.
    - `association`: The name of the association whose fetch strategy is being overridden.
    - `mode`: The fetching strategy used for the association, defaulting to `JOIN`.
    - `fetch`: The timing of the association fetching, defaulting to `EAGER`.

## Example

```java
@FetchProfile(
    name = "userWithOrders",
    fetchOverrides = {
        @FetchOverride(entity = User.class, association = "orders", mode = FetchMode.JOIN, fetch = FetchType.EAGER)
    }
)
public class User {
    // User properties and methods
}
```