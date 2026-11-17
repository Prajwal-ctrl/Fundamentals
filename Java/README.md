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