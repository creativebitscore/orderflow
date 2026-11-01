# Resume entry
## OrderFlow — Event-Driven E-Commerce Microservices Platform | Java 21, Spring Boot
- Built seven independently runnable Spring Boot services behind Spring Cloud Gateway with JWT/BCrypt authentication, Flyway migrations, and isolated PostgreSQL schemas.
- Implemented RabbitMQ Saga checkout across Order, Inventory, and Payment services with idempotent consumers, atomic stock reservation, failure compensation, durable queues, retries, and DLQ routing.
- Added Redis-backed product/cart caching, paginated search, role claims, refresh-token rotation, simulated idempotent payments, and React/TypeScript client workflows.
- Created Maven/JUnit automation, Docker Compose for a resource-conscious local stack, OpenAPI endpoints, CI, and a reproducible HTTP load script that reports measured latency, throughput, and failures.

**Complexity:** maintains business state across independently committed services without distributed ACID while preventing overselling and handling duplicate asynchronous delivery.
