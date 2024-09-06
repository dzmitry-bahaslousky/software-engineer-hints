**The Dependency Rule** is a fundamental principle in [[Clean Architecture]] that dictates how different layers of an application should interact with each other. The rule ensures that the core business logic is isolated and independent from external layers, making the system more robust, maintainable, and adaptable to change.

### Key Points of The Dependency Rule:

1. **Inward Dependencies**:
    - Dependencies in the system should always point inward, toward the core of the application. This means that:
	     The outer layers (e.g., frameworks, user interfaces, databases) depend on the inner layers (e.g., use cases, business logic), but not the other way around.
2. **No Outward Dependencies**:
    - Inner layers (like business rules) must not depend on any details from outer layers (like UI or databases). The core logic should have no knowledge of or reliance on external systems or implementation details.
4. **Interface-Based Communication**:
    - To adhere to the Dependency Rule, inner layers often communicate with outer layers through interfaces. This allows the core logic to define what it needs without being tied to a specific implementation, enabling easy substitution or modification of outer layer components.