https://microservices.io/patterns/decomposition/decompose-by-business-capability.html

**Decompose by Business Capability** is a microservices decomposition pattern where the system is divided based on core **business functions** or capabilities. Each microservice is responsible for a distinct business capability, representing a self-contained part of the organization's operations.

### Key Concepts:

- **Business Capability:** A specific function or area of the business that delivers value, such as `Sales`, `Inventory`, `Payments`, or `Customer Management`.
- **Microservice Alignment:** Each microservice is aligned with one business capability, ensuring that the service focuses on a specific business area.
- **End-to-End Responsibility:** The microservice manages everything related to its capability, including business logic, data, and interactions with other services.

### Example:

In an **e-commerce application**, business capabilities might include:

- **Order Service:** Manages the process of placing and tracking customer orders.
- **Payment Service:** Handles payment processing, refunds, and transactions.
- **Inventory Service:** Manages stock levels, product availability, and warehouse operations.
- **Shipping Service:** Oversees the logistics of delivering orders to customers.
- **Customer Service:** Manages customer information, profiles, and communications.

Each of these services corresponds to a specific business capability and operates independently of the others.

### Benefits:

- **Organizational Alignment:** Microservices mirror the structure of the business, making it easier for teams to focus on specific functions.
- **Independent Development:** Teams can develop, deploy, and scale services independently based on the needs of the business function.
- **Flexibility:** Changes to one business capability don’t affect others, minimizing risks and dependencies.
- **Better Scaling:** Services can be scaled based on demand (e.g., `Order Service` might need more resources during high shopping seasons, while `Inventory Service` might not).

### Challenges:

- **Complexity in Coordination:** As services are decoupled, coordinating workflows across multiple services can introduce complexity.
- **Cross-Service Communication:** Ensuring effective communication between services, especially if they need to collaborate on certain tasks.
- **Data Duplication:** Different services may need to manage overlapping data, leading to data duplication and consistency challenges.

This decomposition pattern allows an organization to evolve its architecture in line with business goals, offering agility and flexibility in responding to market needs.

### How to identify business capabilities? 

Identifying business capabilities and hence services requires an understanding of the business. An organization’s business capabilities are identified by analyzing the organization’s purpose, structure, business processes, and areas of expertise. Bounded contexts are best identified using an iterative process. Good starting points for identifying business capabilities are:
- organization structure - different groups within an organization might correspond to business capabilities or business capability groups.
- high-level domain model - business capabilities often correspond to domain objects