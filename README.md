# cloud-architecture-notes
This repository contains my learning progress in System Design and Cloud Concepts. Below is a table of contents linking to specific topics covered.

## Table of Contents

| Topic                          | Description                                                                                   |
|--------------------------------|-----------------------------------------------------------------------------------------------|
| [Software Architecture](#software-architecture) | Overview of core principles, design steps, and architecture evolution |
| [System Design Components](#system-design-components) | Key system components for scalable and efficient architecture |
| [References](#references) | Resources and materials referenced in these notes |

## Software Architecture

Software architecture defines the high-level structure of a system and the critical decisions shaping its functionality, performance, scalability, and adaptability. A well-designed architecture balances these requirements, providing a solid foundation for both current and future development.

### Key Design Steps

Designing effective software architecture involves the following steps:

1. **Requirements Gathering**: Engage stakeholders to identify and document both functional and non-functional requirements that the architecture must satisfy.
2. **Define Goals**: Establish clear architectural goals based on requirements, such as performance, scalability, maintainability, and security.
3. **Select Patterns**: Choose architectural patterns (e.g., microservices, monolith, event-driven) that align with project goals and system requirements.
4. **Design Components**: Decompose the system into modular components, defining each component’s responsibilities, interactions, and interfaces.
5. **Choose Technology Stack**: Select technologies, languages, and tools that best support the architecture’s goals and requirements.
6. **Create Diagrams**: Use architectural diagrams (e.g., component, sequence, deployment) to clearly document relationships and data flows.
7. **Evaluate and Refine**: Review the design with stakeholders and adjust as needed to meet all goals and requirements.
8. **Document Architecture**: Prepare detailed documentation with descriptions, diagrams, and guidance for both implementation and maintenance.
9. **Prototype**: Build prototypes or proofs of concept to validate architectural choices or critical components.
10. **Iterate and Improve**: Use feedback and testing results to refine the architecture, revisiting earlier steps if necessary.
11. **Implementation Planning**: Plan the implementation timeline, resource allocation, and team responsibilities to execute the design effectively.

### Architecture Evolution

As development progresses, architecture adapts to integrate specific technologies, manage dependencies, and prepare for long-term growth. This evolution process distinguishes high-level design principles from implementation details, ensuring the architecture can meet future demands while remaining maintainable.

## System Design Components

In system design, creating a robust and scalable architecture requires selecting the right components that work together to ensure efficiency, availability, and maintainability. Below are key components that make up a distributed system.

### Key Components in System Design
1. **Load Balancer**: 
   - **What it is**: A load balancer distributes incoming traffic across multiple servers to prevent any single server from being overwhelmed. 
   - **Use Case**: In a web application with millions of users, the load balancer ensures that user requests are distributed evenly across several backend servers, maintaining system performance and availability. Without it, one server could become overloaded, causing delays or failures.

2. **Key-value Stores** (e.g., Redis, DynamoDB): 
   - **What it is**: A key-value store is a fast data storage system that retrieves values based on keys, providing low-latency access to frequently used data. 
   - **Use Case**: On an e-commerce website, a key-value store might be used to cache product details so they are retrieved instantly when users view product pages, instead of querying the database every time.

3. **Blob Storage & Databases** (e.g., Amazon S3, MongoDB):
   - **What they are**: Blob storage is used to store large, unstructured data, such as images or videos, while databases store structured data. 
   - **Use Case**: For a media streaming service, videos are stored in blob storage, and user data, such as login information and playlists, are stored in a database for easy querying and updates.

4. **Rate Limiters**:
   - **What they are**: Rate limiters control the number of requests a user can make in a given time to prevent abuse or overloading the server. 
   - **Use Case**: In an API service, a rate limiter might restrict the number of requests a user can make per minute, preventing system crashes due to excessive traffic.

5. **Monitoring System** (e.g., Prometheus, Grafana):
   - **What it is**: A monitoring system tracks the health and performance of the system in real-time. 
   - **Use Case**: On a high-traffic website, the monitoring system tracks server CPU usage, memory consumption, and error rates. If CPU usage spikes, an alert is triggered to notify the team so they can investigate and resolve the issue.

6. **Distributed Messaging Queue** (e.g., Kafka, RabbitMQ):
   - **What it is**: A messaging queue allows services to communicate asynchronously by queuing messages for later processing. 
   - **Use Case**: In an online banking system, a messaging queue can handle transaction requests, ensuring each request is processed in order without overloading the system.

7. **Distributed Unique ID Generator**:
   - **What it is**: A generator that produces globally unique identifiers (UUIDs) across multiple services.
   - **Use Case**: In a large-scale order management system, unique order IDs are generated across microservices to ensure that orders are identifiable and there are no conflicts.

8. **Distributed Search** (e.g., Elasticsearch):
   - **What it is**: Distributed search engines index large volumes of data and provide fast, real-time search capabilities.
   - **Use Case**: On an online store, distributed search helps users quickly find products by keyword, returning search results almost instantly, even with thousands of products in the catalog.

9. **Distributed Logging Service** (e.g., ELK Stack, Splunk):
   - **What it is**: A distributed logging system aggregates logs from various services, enabling centralized monitoring and troubleshooting.
   - **Use Case**: In a microservices architecture, a distributed logging service aggregates logs from different services, allowing developers to trace errors and troubleshoot issues across services efficiently.

10. **Distributed Task Scheduler** (e.g., Apache Airflow):
    - **What it is**: A distributed task scheduler automates and manages the execution of tasks across different systems.
    - **Use Case**: In a data processing pipeline, a task scheduler orchestrates tasks like data cleaning, transformation, and loading (ETL), ensuring the right tasks are executed at the right times.

### Primary Bottlenecks in System Design
As systems scale, certain components can become bottlenecks that limit overall performance. Some common bottlenecks include:

- **Database Performance**: A database can become a bottleneck when it struggles to handle high volumes of queries or large datasets. Techniques such as indexing, sharding, and caching can help alleviate this issue.
- **Network Latency**: Communication delays between services or components can slow down the system. Reducing network hops, optimizing protocols, and caching data closer to the user can help minimize latency.
- **CPU and Memory Limitations**: If a system is CPU or memory-bound, it may struggle to process large volumes of requests. Vertical scaling (adding more resources to a single machine) or horizontal scaling (adding more machines) can address these limitations.
- **Disk I/O**: Slow disk access can be a significant bottleneck, especially for systems that rely on heavy read/write operations. Using faster storage solutions (e.g., SSDs) or optimizing data storage strategies can help.
- **Service Dependencies**: Systems often rely on third-party services or microservices, which can become points of failure or cause delays if not properly managed. Redundancy, failover strategies, and service monitoring are essential for minimizing downtime.

## References

- GeeksforGeeks: [System Design Tutorial](https://www.geeksforgeeks.org/system-design-tutorial/)
- A Dev' Story: [Software Architecture and Design](https://youtube.com/playlist?list=PL4JxLacgYgqTgS8qQPC17fM-NWMTr5GW6&si=-p_YmwfQFnmiiTZn)
- freeCodeCamp.org: [System Design Concepts](https://www.youtube.com/watch?v=F2FmTdLtb_4)
- ByteByteGo: [System Design Interview](https://www.youtube.com/watch?v=i7twT3x5yv8&t=1s)