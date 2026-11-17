# Core Java Learning Roadmap

This folder tracks our journey through Java fundamentals, internals, practical coding exercises and interview-level reasoning.

## 1. Java platform and execution
- JDK, JRE/runtime and JVM: responsibilities and differences
- Java source compilation and class files
- Bytecode and platform independence
- Class loading, linking, verification and initialization
- Interpreter, JIT compiler and execution lifecycle
- Java versions and class-file compatibility

## 2. Language fundamentals and types
- Primitive types and reference types
- Variables, scope, lifetime and default values
- Type conversion, casting and promotion
- Operators, control flow and loops
- Pass-by-value semantics
- Wrapper classes, autoboxing and unboxing

## 3. Object-oriented programming
- Classes, objects, fields, methods and constructors
- Encapsulation and access modifiers
- Inheritance and composition
- Polymorphism: overloading and overriding
- Abstraction, interfaces and abstract classes
- static, final and this/super
- Object class methods and contracts

## 4. Strings and immutability
- String pool and string interning
- String immutability
- StringBuilder vs StringBuffer
- equals() vs ==
- Designing immutable classes

## 5. Exception handling
- Throwable hierarchy
- Checked vs unchecked exceptions
- try/catch/finally and try-with-resources
- throw vs throws
- Custom exceptions
- Exception propagation and best practices

## 6. Collections Framework
- Collection hierarchy: List, Set, Queue and Deque
- ArrayList vs LinkedList
- HashSet, LinkedHashSet and TreeSet
- HashMap, LinkedHashMap, TreeMap and Hashtable
- Queue, PriorityQueue and Deque
- Iterator, ListIterator and fail-fast behavior
- Internal working, hashing, collisions and resizing
- Choosing collections using complexity and access patterns

## 7. Generics
- Generic classes, methods and interfaces
- Type parameters and bounds
- Wildcards: ?, extends and super
- PECS principle
- Type erasure and limitations

## 8. Equality, ordering and object contracts
- equals() and hashCode()
- Hash-based collection requirements
- Comparable vs Comparator
- Natural ordering and custom sorting
- Mutable keys and collection correctness

## 9. Functional programming and streams
- Functional interfaces
- Lambda expressions and method references
- Predicate, Function, Consumer and Supplier
- Stream creation and pipeline
- Intermediate vs terminal operations
- map, filter, flatMap, reduce and collect
- Collectors: groupingBy, partitioningBy, joining and aggregations
- Optional and null-safe API design
- Parallel streams and trade-offs

## 10. Concurrency and multithreading
- Process vs thread
- Thread lifecycle and creation
- Runnable and Callable
- synchronized and intrinsic locks
- volatile and Java Memory Model basics
- Atomic classes and race conditions
- ExecutorService and thread pools
- CompletableFuture
- ConcurrentHashMap and concurrent collections
- Deadlocks, starvation and visibility

## 11. JVM memory and garbage collection
- Runtime data areas: heap, stacks, method area/metaspace, PC registers
- Object allocation and references
- Stack vs heap
- Garbage collection fundamentals
- GC roots and reachability
- Common collectors and high-level trade-offs
- Memory leaks and troubleshooting
- JVM monitoring and diagnostic tools

## Practice and documentation convention
For each topic, add a dedicated Markdown file with:
1. Problem and motivation
2. Conceptual explanation and internal working
3. Diagrams or execution flow where useful
4. Runnable examples
5. Basic, intermediate and advanced exercises
6. Solutions and complexity/trade-offs
7. Interview questions
8. Official references

Use Java 17 as the initial baseline unless a topic explicitly compares versions.

---

## 🔴 Interview-focused additions for a 2–3 YOE backend developer

The topics below are explicitly added because a developer at this experience level is expected to reason about behavior, edge cases and production impact—not only recite definitions. The red marker 🔴 identifies interview-critical additions or deeper coverage that was missing from the initial roadmap.

### 🔴 12. Complexity analysis and coding fundamentals
- Big-O time and space complexity; best, average and worst cases
- Arrays, strings, two pointers, sliding window and prefix sums
- Hashing and frequency maps
- Sorting, binary search and comparator-based ordering
- Stack, queue, deque and heap / priority queue
- Recursion and basic backtracking
- Common patterns: grouping, deduplication, top-K, intervals
- Choosing a data structure from operation requirements
- Explain complexity and edge cases while coding

### 🔴 13. Modern Java features interviewers may expect
- Java 8 baseline: lambdas, streams, Optional, default methods, java.time
- Java 11: local-variable syntax in lambda parameters, modern APIs and runtime awareness
- Java 17: records, sealed classes, pattern matching for instanceof, text blocks
- Java 21: virtual threads, record patterns, pattern matching for switch, sequenced collections
- Java 25: module import declarations, compact source files and instance main methods, flexible constructor bodies; recognize preview features and distinguish preview from final
- LTS releases and class-file compatibility: 17, 21 and 25
- Decide whether a feature is appropriate for an existing production codebase

### 🔴 14. API, I/O and application-level Java
- java.time: Instant, LocalDate, LocalDateTime, ZonedDateTime and time-zone mistakes
- Files, streams, buffered I/O and resource management
- Serialization basics and why native Java serialization needs caution
- BigDecimal for money; scale, rounding and precision
- Enum design and EnumMap / EnumSet
- Defensive copying and immutable value objects
- Basic networking and HTTP client awareness

### 🔴 15. Deeper concurrency and runtime reasoning
- Java Memory Model and happens-before
- Atomicity, visibility and ordering
- synchronized vs volatile vs atomic classes
- ReentrantLock, read-write locks and optimistic reads
- ConcurrentHashMap internals at a conceptual level
- Executor sizing, bounded queues, rejection policies and shutdown
- CompletableFuture composition, exception handling and blocking pitfalls
- Virtual threads: suitable workloads, pinning awareness and limits
- ThreadLocal risks in pooled threads
- Deadlock diagnosis, thread dumps and Java Flight Recorder basics

### 🔴 16. Interview coding and explanation standard
For every coding exercise, be ready to:
1. Clarify input constraints and expected output.
2. Explain a straightforward solution first.
3. Improve it using the right data structure or algorithm.
4. State time and space complexity.
5. Test null/empty input, duplicates, boundaries and large input.
6. Explain readability and maintainability trade-offs.

## Interview questions and practical drills

See [Interview-Questions.md](Interview-Questions.md). It contains a question bank for Core Java, collections, streams, concurrency, JVM, modern Java and coding exercises.

## Version and market-awareness note — 17 November 2026

- Keep **Java 17** as the first implementation baseline so foundational concepts remain clear.
- Be able to discuss **Java 21** features, especially virtual threads, because it is an LTS release and relevant to modern backend services.
- Know what changed in **Java 25**, also an LTS release. Learn stable features first; identify preview/incubator features rather than presenting them as universally production-ready.
- Interviewers may ask about Java 8/11/17 in existing enterprise codebases even when newer LTS releases exist. Always ask which version the target project uses.

Official references:
- [Java SE support roadmap](https://www.oracle.com/java/technologies/java-se-support-roadmap.html)
- [Java 25 release](https://www.oracle.com/news/announcement/oracle-releases-java-25-2025-09-16/)
- [Java 21 documentation](https://docs.oracle.com/en/java/javase/21/)
- [Java 25 documentation](https://docs.oracle.com/en/java/javase/25/)
