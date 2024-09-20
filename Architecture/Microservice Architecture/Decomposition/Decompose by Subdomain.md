https://microservices.io/patterns/decomposition/decompose-by-subdomain.html

**Decomposition by Subdomain** is a microservices architecture pattern rooted in **Domain-Driven Design (DDD)**. It involves breaking down a system based on **business subdomains**, where each microservice represents a distinct "bounded context" corresponding to a subdomain in the overall business domain.
### Key Concepts:

- **Domain:** The overall business problem space or area of interest (e.g., e-commerce, banking).
- **Subdomain:** A specific part of the domain that has its own unique rules and logic. Subdomains can be **core**, **supporting**, or **generic**:
    - **Core Subdomain:** The most important, unique part of the business (e.g., in e-commerce, `Order Management`).
    - **Supporting Subdomain:** Helps the core subdomain (e.g., `Customer Support` in e-commerce).
    - **Generic Subdomain:** Standard or commodity parts of the business (e.g., `Billing`).
- **Bounded Context:** Each microservice has a clearly defined boundary in which the data model and business logic are specific to that subdomain.

### Example:

In an **e-commerce** platform, the system might be divided into the following subdomains:

- **Core Subdomain:** `Order Processing`
- **Supporting Subdomains:** `Inventory Management`, `Payment Processing`
- **Generic Subdomain:** `Customer Support`, `Billing`

Each subdomain would correspond to its own microservice, which operates independently, with its own logic, data, and responsibilities.

### Benefits:

- **Alignment with Business Logic:** Services are designed to closely mirror business processes, making them more intuitive and easier to manage.
- **Isolated Boundaries:** Services operate within a well-defined context, reducing dependencies between services.
- **Focused Teams:** Teams can work independently on specific subdomains without affecting others.

### Challenges:

- **Communication Between Services:** Services often need to interact, requiring efficient handling of cross-boundary communication.
- **Consistency:** Managing consistency across services, especially with shared data between subdomains, can be complex.

Decomposition by subdomain ensures that services are built with a deep understanding of business logic, making the architecture more modular and aligned with the organization’s structure.

### How to identify the subdomains?

Identifying subdomains and hence services requires an understanding of the business. Like business capabilities, subdomains are identified by analyzing the business and its organizational structure and identifying the different areas of expertise. Subdomains are best identified using an iterative process. Good starting points for identifying subdomains are:
- organization structure - different groups within an organization might correspond to subdomains
- high-level domain model - subdomains often have a key domain object