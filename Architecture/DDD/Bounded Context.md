**Bounded Context** is a core concept in **[[Domain-Driven Design]] (DDD)** that defines clear boundaries within which a specific domain model is consistent and well-defined. Inside these boundaries, terms, rules, and behavior are coherent, and there is no ambiguity about the meaning of domain concepts.

### Key Characteristics of Bounded Context:

1. **Model Boundaries**:
    - A Bounded Context establishes the limits within which terms and concepts of the domain are used consistently. Outside these boundaries, other models may exist with similar terms but different meanings.
2. **Separation of Concerns**:
    - Each Bounded Context is responsible for a specific part of the domain, avoiding confusion and overlap between different areas of the system.
3. **Isolation of Changes**:
    - Changes within one Bounded Context should not affect others, allowing the system to be more flexible and maintainable. Each context evolves independently.
4. **Communication Between Contexts**:
    - Different Bounded Contexts interact through integration mechanisms (like APIs, messages, or events) to keep dependencies low and avoid tight coupling between contexts.
5. **Relation to Microservices**:
    - Bounded Contexts often align with microservice boundaries, where each microservice is responsible for its own context, leading to better scalability and separation of responsibilities.

### Example:

In a system with two Bounded Contexts — **Order Management** and **Customer Management** — the term "Customer" may refer to different things. In the **Order Management** context, it represents order-specific information, while in **Customer Management**, it refers to customer preferences and profile data. Each context maintains its own distinct model of "Customer."

### Benefits of Bounded Context:

- **Clarity and Simplicity**: Clear boundaries help reduce confusion about domain concepts.
- **Improved Modularity**: Each context can be developed, maintained, and changed independently.
- **Scalability**: You can isolate and scale different parts of the system based on their context.
- **Easier Maintenance**: Since changes are confined within a context, the risk of unintended side effects in other parts of the system is reduced.

**Bounded Context** enables the division of complex domains into smaller, manageable parts, making systems easier to understand, evolve, and maintain. It ensures consistency within contexts while allowing for variation between them.