# Spring Boot Interview Question Bank — 2–3 Years Experience

Answer with request flow, object lifecycle, proxy behavior, transaction boundaries and failure scenarios—not just annotation definitions.

## A. Spring core and IoC
1. What problem does Spring solve compared with manually creating objects?
2. Explain IoC and dependency injection with a concrete example.
3. BeanFactory vs ApplicationContext?
4. What happens during component scanning and bean creation?
5. Explain the lifecycle of a singleton bean.
6. @Component vs @Service vs @Repository vs @Bean?
7. Why is constructor injection generally preferred?
8. What happens when two beans of the same type exist? Explain @Primary and @Qualifier.
9. What are bean scopes? Is a singleton bean automatically thread-safe?
10. How can circular dependencies occur, and why are they a design warning?

## B. Spring Boot and web request lifecycle
11. What does @SpringBootApplication combine?
12. How does auto-configuration decide which beans to create?
13. Walk through an HTTP request from embedded server to controller and response.
14. Filter vs HandlerInterceptor vs AOP?
15. @Controller vs @RestController?
16. @PathVariable vs @RequestParam vs @RequestBody?
17. How do you validate input and return consistent error responses?
18. How do you design pagination and sorting without exposing database entities?
19. PUT vs PATCH; which HTTP methods are idempotent?
20. How would you make a payment or create-order endpoint safe against client retries?

## C. Transactions and persistence
21. How does @Transactional work under the hood?
22. Why might @Transactional not work on self-invocation?
23. What are propagation modes REQUIRED, REQUIRES_NEW and SUPPORTS?
24. What are isolation levels? How do they relate to database isolation?
25. Which exceptions trigger rollback by default? How do rollback rules change it?
26. What is the persistence context / first-level cache?
27. Explain transient, managed, detached and removed entity states.
28. What are dirty checking and flush? Is flush the same as commit?
29. Lazy vs eager loading; what is the N+1 query problem?
30. How would you solve N+1? Compare fetch join, entity graph, batch fetching and DTO projection.
31. Optimistic vs pessimistic locking; when would you use each?
32. What is the difference between save(), flush() and saveAndFlush() in Spring Data JPA?

## D. Security, distributed systems and production
33. Authentication vs authorization; explain a JWT-based request flow.
34. CORS vs CSRF?
35. How do timeout, retry and circuit breaker patterns differ?
36. Why can retries create duplicate writes? Explain idempotency.
37. Explain Kafka topic, partition, offset and consumer group.
38. How do you handle duplicate message delivery and failed messages?
39. What is the transactional outbox pattern and which dual-write problem does it address?
40. How would you trace a slow API across controller, service, connection pool and database?
41. What happens when HikariCP runs out of available connections?
42. How do readiness and liveness probes differ?

## E. Testing
43. Unit test vs @WebMvcTest vs @DataJpaTest vs @SpringBootTest?
44. What should be mocked, and what should use a real database?
45. How do you test exception handling and validation?
46. How would you test a transaction rollback?
47. What does Testcontainers provide over an in-memory database for integration testing?

## F. Practical design exercises
48. Design a paginated endpoint with filtering and stable ordering.
49. Design a retry-safe create-payment endpoint.
50. A service method updates PostgreSQL and publishes Kafka. What failure window exists, and how would you close it?
51. An endpoint is slow only under load. List a diagnostic sequence before changing code.
52. A scheduled task runs on multiple application replicas. How do you prevent duplicate processing?

## Interview execution checklist
Use a real scenario where possible. Explain the request path, relevant Spring proxy/container behavior, database interaction, failure mode, tests and operational verification. Distinguish what you personally implemented from what your team or platform handled.
