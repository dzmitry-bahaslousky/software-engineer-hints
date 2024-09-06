**Vertical Scaling**, also known as **scaling up**, is the process of increasing the capacity and performance of a single node in a system by adding more resources to it. This can include upgrading hardware components such as CPUs, memory (RAM), and storage to improve the system's overall performance and ability to handle larger workloads.

### Key Characteristics of Vertical Scaling:

1. **Resource Augmentation**: Vertical scaling involves enhancing existing resources rather than adding new ones. This can mean installing more powerful processors, increasing RAM, or upgrading storage to faster disks.

2. **Simplicity in Management**: Since all resources are consolidated in a single machine, management becomes simpler. There’s no need for complex configurations for load balancing or distributed systems.
 
3. **Limitations**: Vertical scaling has physical and financial limitations. There is only so much hardware that can be added to a single node, and costs can increase significantly for high-end components.

4. **Minimal Changes Required**: Typically, vertical scaling does not require significant changes to the application architecture or code, making it easier to implement.

### Examples of Vertical Scaling:

- Upgrading a server from 16 GB of RAM to 64 GB to handle more data processing.
- Replacing a CPU with a more powerful multi-core processor to improve performance.

### When to Use Vertical Scaling:

- When an application or system cannot be easily distributed across multiple nodes.
- When a quick solution is needed to enhance performance without redesigning the system architecture.
- When budget constraints make it impractical to invest in additional hardware for horizontal scaling.