# Java Interview Question Bank — 2–3 Years Experience

Use these questions to practise explaining behavior, writing code and defending trade-offs. Do not memorize one-line answers. For each answer, include a small example, edge case and complexity where applicable.

## A. Core language and OOP
1. Is Java pass-by-value or pass-by-reference? Demonstrate with an object mutation and reassignment.
2. Explain overloading vs overriding. How does runtime dispatch work?
3. Interface vs abstract class: what changes with default, static and private interface methods?
4. Composition vs inheritance: when would you choose each?
5. Why is String immutable? What practical guarantees does it provide?
6. What is the difference between == and equals()?
7. Explain checked vs unchecked exceptions. When would you create a custom exception?
8. What happens if an exception is thrown in finally? What should be avoided there?
9. Why use BigDecimal for money instead of double?
10. Explain equals() and hashCode() contracts. What breaks if a key's hash-relevant field changes after insertion into a HashMap?

## B. Collections and generics
11. Explain HashMap put() and get() at a conceptual level, including hashing, bucket selection, collision handling and resizing.
12. What happens when two keys have the same hash code?
13. Why must equals() and hashCode() be consistent?
14. ArrayList vs LinkedList: compare access, insertion, memory overhead and real-world usage.
15. HashMap vs LinkedHashMap vs TreeMap: what ordering and complexity do they provide?
16. HashSet internally uses which collection conceptually?
17. Comparable vs Comparator: show multi-field sorting.
18. What is fail-fast iteration? Is it a thread-safety guarantee?
19. What problem does ConcurrentHashMap solve? Why is HashMap unsafe for concurrent structural modification?
20. Explain PECS with a producer and consumer example.

## C. Streams and functional programming
21. map() vs flatMap(): demonstrate with nested lists.
22. What is lazy evaluation in streams?
23. Can a stream be reused after a terminal operation?
24. groupingBy() vs partitioningBy(): when would you use each?
25. How would you calculate count, sum and average per department in one pass?
26. When can parallel streams make performance worse?
27. What is the purpose of Optional? Why is Optional generally a poor choice for entity fields or method parameters?

## D. Concurrency and JVM
28. Explain race condition, atomicity, visibility and ordering.
29. What does volatile guarantee, and what does it not guarantee?
30. synchronized vs ReentrantLock vs AtomicInteger.
31. What is happens-before in the Java Memory Model?
32. How can a deadlock occur? How would you prevent and diagnose one?
33. How do ExecutorService and thread pools work? Why bound the work queue?
34. Future vs CompletableFuture; thenApply() vs thenCompose().
35. What are virtual threads? Which workloads benefit, and what bottlenecks remain?
36. Explain heap, thread stack and metaspace.
37. What makes an object eligible for garbage collection? What are GC roots?
38. How would you investigate high CPU, high memory or a thread stuck in production?

## E. Modern Java and coding
39. What are records and when are they useful?
40. What are sealed classes?
41. What does pattern matching for instanceof improve?
42. What are virtual threads in Java 21, and how are they different from platform threads?
43. Which Java 25 features have become final, and which are preview/incubator? Verify against the exact JDK documentation.
44. Given a list of employees, group by department and find the highest-paid employee in each group.
45. Find the first non-repeating character in a string.
46. Find the top K frequent elements in an integer array.
47. Merge overlapping intervals.
48. Find the longest substring without repeating characters.
49. Given transactions, detect duplicate transaction IDs and explain the data structure and complexity.
50. Implement an LRU cache and explain its operations' complexity.

## F. Interview execution checklist
For coding questions: clarify assumptions, propose a simple solution, optimize, state time/space complexity, test edge cases and explain trade-offs.

For conceptual questions: answer in this order — definition, problem solved, internal behavior, example, limitation/trade-off, production use.

For every topic, prepare one story from actual work: the problem, your role, diagnosis, fix, verification and measurable result. Never claim production experience you did not have.
