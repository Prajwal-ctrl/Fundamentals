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