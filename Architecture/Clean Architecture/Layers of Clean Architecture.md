In **[[Clean Architecture]]**, an application is divided into several layers, each serving a specific purpose. The main layers are **Entities**, **Use Cases**, **Interface Adapters**, and **Frameworks & Drivers**. Here’s a brief overview of each:

### 1. **Entities**

- **Description**: This is the innermost layer that contains the core business rules and logic. Entities represent the fundamental business objects and concepts, encapsulating the rules and behaviors critical to the business.
- **Role**: Entities are independent of other layers. They do not depend on any frameworks, databases, or external systems. Their focus is purely on the business logic, regardless of how or where it will be used or implemented.
- **Example**: In an order management system, an entity might be "Order," which contains rules about order status, calculations, discounts, etc.

### 2. **Use Cases**

- **Description**: This layer contains the application-specific business logic that defines how entities interact with one another to fulfill a particular use case. Use cases implement specific actions or processes within the system.
- **Role**: Use cases orchestrate the flow of data and interactions between entities. They communicate with other layers through interfaces and should not depend on specific frameworks or technologies.
- **Example**: In an order management system, a use case might be "PlaceOrder," which handles the process of creating a new order, calculating the total price, checking inventory, and notifying the customer.

### 3. **Interface Adapters**

- **Description**: This layer is responsible for converting data between the formats used by the application and those used by external systems. It acts as a bridge between the business logic and the outside world.
- **Role**: Interface Adapters convert data from the external world (e.g., databases, web interfaces) into a format that the use cases and entities can understand, and vice versa.
- **Example**: Web controllers that handle HTTP requests and pass them to the use cases, or repositories that fetch data from a database and convert it into entity objects.

### 4. **Frameworks & Drivers**

- **Description**: This is the outermost layer, encompassing all external technologies and tools used by the application. This could include databases, web services, UI frameworks, and other systems.
- **Role**: Frameworks and Drivers provide the technical implementations needed for the application to function but should be kept separate from the core business logic. While these frameworks depend on the inner layers, the inner layers should not depend on them.
- **Example**: A database management system (DBMS), a web framework like Spring for dependency management, or external APIs used for system integration.