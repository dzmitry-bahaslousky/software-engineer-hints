**Horizontal Scaling**, also known as **scaling out**, is the process of adding more nodes or instances to a system to distribute the workload and increase capacity. Instead of upgrading a single machine, horizontal scaling involves expanding the system by adding multiple machines or servers to handle increased demand.

### Key Characteristics of Horizontal Scaling:

1. **Addition of Nodes**: In horizontal scaling, new servers or instances are added to the existing infrastructure, allowing the system to share the load among multiple machines.

2. **Load Distribution**: Workloads are distributed across multiple nodes, which helps in balancing the load and improving overall performance. This can lead to better resource utilization.

3. **High Availability and Fault Tolerance**: By using multiple servers, horizontal scaling enhances the system's resilience. If one server fails, others can continue to operate, ensuring higher availability.

4. **Scalability Beyond Limits**: Unlike vertical scaling, which has physical limitations, horizontal scaling can continue to add nodes as needed, making it more suitable for applications with rapidly growing workloads.

5. **Complexity**: While horizontal scaling offers many benefits, it can also introduce complexity in terms of infrastructure management, [[Load Balancer|load balancing]], and data consistency across nodes.

### Examples of Horizontal Scaling:

- Adding more web servers to handle increased traffic for a website.
- Deploying multiple database instances to distribute read and write operations across different servers.

### When to Use Horizontal Scaling:

- When dealing with applications that require high availability and fault tolerance.
- When the workload is expected to grow significantly over time, making it necessary to add resources continuously.
- When the application can be distributed across multiple nodes without significant architectural changes.