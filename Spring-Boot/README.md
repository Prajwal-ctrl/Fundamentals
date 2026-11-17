# Spring Framework & Spring Boot Learning Roadmap

This folder tracks the Spring fundamentals that explain how a Spring application is constructed, configured, executed and connected to databases.

## 1. Why Spring and Spring Boot?
- Problems with tightly coupled application code
- Dependency management and object lifecycle
- Spring Framework vs Spring Boot
- Convention over configuration
- Embedded servers and production-ready defaults

## 2. IoC and Dependency Injection
- Inversion of Control (IoC)
- Dependency Injection (DI)
- Constructor, setter and field injection
- Dependency inversion principle
- Loose coupling and testability
- Bean resolution and ambiguity

## 3. Spring container and beans
- BeanFactory vs ApplicationContext
- Bean definitions and component scanning
- @Component, @Service, @Repository and @Controller
- @Configuration and @Bean
- Bean scopes: singleton, prototype, request, session
- Bean lifecycle and lifecycle callbacks
- @PostConstruct and @PreDestroy
- Circular dependencies and their risks
- @Primary and @Qualifier

## 4. Configuration and auto-configuration
- Application startup lifecycle
- @SpringBootApplication
- Conditional configuration
- Auto-configuration discovery and ordering
- Starter dependencies
- application.properties and application.yml
- Externalized configuration and @ConfigurationProperties
- Profiles and environment-specific configuration

## 5. Spring MVC and REST APIs
- DispatcherServlet and request lifecycle
- @RestController and @Controller
- Request mappings and HTTP methods
- @PathVariable, @RequestParam and @RequestBody
- DTOs and entity boundaries
- Validation and @Valid
- HTTP status codes and ResponseEntity
- Serialization and Jackson basics

## 6. Filters, interceptors and exception handling
- Servlet filters
- HandlerInterceptors
- AOP overview and cross-cutting concerns
- @ControllerAdvice and @ExceptionHandler
- Consistent error response design
- Request tracing and logging

## 7. Transactions
- ACID fundamentals
- @Transactional behavior
- Propagation and isolation
- Rollback rules
- Proxy-based interception and self-invocation
- Transaction boundaries
- Read-only transactions
- Database locks and concurrency implications

## 8. Persistence: Spring Data JPA and Hibernate
- JDBC vs JPA vs Hibernate vs Spring Data JPA
- Entity lifecycle and persistence context
- Entity mapping and identifiers
- Relationships and ownership
- Fetch types and N+1 problem
- Cascades and orphan removal
- JPQL, native queries and projections
- Pagination and sorting
- Dirty checking and flush
- Optimistic and pessimistic locking
- Connection pools and HikariCP

## 9. Testing
- Unit tests and Mockito
- Spring context tests
- @WebMvcTest and @DataJpaTest
- @SpringBootTest
- Testcontainers and database integration tests
- Testing transactions and failure cases

## 10. Production fundamentals
- Actuator and health checks
- Logging and correlation IDs
- Metrics and tracing
- Graceful shutdown
- External secrets and configuration
- Timeouts, retries and resilience basics
- Thread pools and request concurrency

## Practice and documentation convention
For each topic, create a dedicated Markdown file containing motivation, internals, code examples, practical scenarios, exercises, solutions, trade-offs and official references. Runnable examples should be added to a small project when the topic benefits from execution.

---

## 🔴 Interview-focused additions for a 2–3 YOE backend developer

The red marker 🔴 identifies interview-critical topics that were missing or need stronger practical coverage. Expect scenario questions: what happens, why it happens, how to reproduce it, and how to fix it.

### 🔴 11. Spring Security and API security
- Authentication vs authorization
- Security filter chain and request processing
- Password hashing vs encryption
- JWT structure, validation, expiry and refresh-token design
- OAuth 2.0 and OpenID Connect concepts
- Role-based and method-level authorization
- CORS vs CSRF
- Secure secret and credential handling
- Common API security mistakes: broken access control, mass assignment and excessive data exposure

### 🔴 12. REST API design beyond annotations
- HTTP methods, safe/idempotent semantics and status codes
- Resource naming and consistent response contracts
- Request validation and error response design
- Pagination, sorting, filtering and stable ordering
- API versioning and backward compatibility
- Idempotency keys for retry-safe write APIs
- Timeouts, retries and duplicate request handling
- Optimistic concurrency using version/ETag concepts
- OpenAPI / Swagger documentation

### 🔴 13. Caching and performance
- Cache-aside pattern and when not to cache
- Spring Cache abstraction
- Redis fundamentals, TTL and eviction
- Cache invalidation and stale data
- Cache stampede / thundering herd
- HTTP caching and ETags
- Measuring latency and throughput before optimizing

### 🔴 14. Microservices and distributed-system fundamentals
- Monolith vs modular monolith vs microservices trade-offs
- Synchronous REST vs asynchronous messaging
- Service discovery and centralized configuration
- API gateway and load balancing
- Timeouts, retries with backoff, circuit breakers and bulkheads
- Idempotent message consumers
- At-least-once delivery and duplicate processing
- Saga / compensating transactions and outbox pattern
- Eventual consistency and distributed transaction limitations
- Correlation IDs and distributed tracing

### 🔴 15. Messaging and Kafka
- Topic, partition, offset, broker and consumer group
- Partition ordering and consumer parallelism
- Delivery semantics and duplicate handling
- Consumer lag and retry / dead-letter strategies
- Producer acknowledgements and idempotence concepts
- Spring Kafka listener and error-handling basics
- Database update plus event publication: dual-write problem and outbox approach

### 🔴 16. Testing and code quality
- JUnit 5 assertions, lifecycle and parameterized tests
- Mockito: mock, stub, verify, argument captor and strictness
- Unit vs slice vs integration vs end-to-end tests
- MockMvc and WebTestClient awareness
- Testcontainers for real database / broker integration
- Testing transaction rollback and concurrent behavior
- Contract testing and API compatibility
- Static analysis, formatting and code review fundamentals

### 🔴 17. Production troubleshooting
- Read stack traces and identify root cause
- Diagnose slow endpoints across application, pool and database
- HikariCP pool sizing, connection leaks and pool exhaustion
- Thread pool saturation and blocked requests
- Heap pressure, memory leaks and GC pauses
- Health/readiness/liveness probes
- Structured logs, metrics, traces and correlation IDs
- Graceful shutdown and in-flight request handling
- Configuration, profiles and secrets across environments

### 🔴 18. Build, delivery and deployment
- Maven lifecycle, dependency scopes and dependency tree
- Gradle awareness
- Docker image, layers, environment configuration and non-root execution
- CI/CD pipeline stages and automated tests
- Kubernetes Pod, Deployment, Service, ConfigMap and Secret fundamentals
- Rolling deployment, readiness and rollback
- Database migration discipline with Flyway or Liquibase

## Interview questions and practical drills

See [Interview-Questions.md](Interview-Questions.md) for scenario-based questions on IoC, bean lifecycle, transactions, JPA, security, REST, microservices, Kafka, testing and production incidents.

## Version and market-awareness note — 17 November 2026

- Understand the Spring Boot 3.x applications commonly found in existing enterprise systems.
- Be aware that Spring Boot **4.1.2** was announced as a stable release on 23 October 2026. Spring Boot **4.2.0-RC2** was announced on 6 November 2026 and is a release candidate, not the same as a final stable release.
- Do not memorize version-specific behavior without checking the exact Spring Boot / Spring Framework version used by the project.
- Use the official release notes and compatibility requirements when selecting a learning-project baseline.

Official references:
- [Spring Boot releases](https://spring.io/blog/category/releases/)
- [Spring Boot 4.1.2 release announcement](https://spring.io/blog/2026/10/23/spring-boot-4-1-2-available-now/)
- [Spring Boot 4.2.0-RC2 announcement](https://spring.io/blog/2026/11/06/spring-boot-4-2-0-RC2-available-now/)
- [Spring Framework reference](https://docs.spring.io/spring-framework/reference/)
- [Spring Boot reference](https://docs.spring.io/spring-boot/reference/)
