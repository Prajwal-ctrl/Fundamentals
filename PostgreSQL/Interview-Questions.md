# SQL & PostgreSQL Interview Question Bank — 2–3 Years Experience

Use the sample schema you create for each exercise. Predict the result before running the query. For performance questions, compare plans on representative data rather than guessing.

## A. SQL and joins
1. INNER JOIN vs LEFT JOIN: what exact rows does each preserve?
2. What changes when a right-table filter is moved from ON to WHERE after a LEFT JOIN?
3. Find employees without a department. Find departments without employees.
4. Why can joining two one-to-many tables inflate SUM() and COUNT()?
5. COUNT(*) vs COUNT(column) vs COUNT(DISTINCT column)?
6. WHERE vs HAVING?
7. NOT IN vs NOT EXISTS: what happens if the subquery returns NULL?
8. UNION vs UNION ALL?
9. How do NULL values behave with =, <>, IS NULL and aggregate functions?
10. When is a self join useful?

## B. Aggregation and complex queries
11. Find average salary by department and filter departments with average salary above a threshold.
12. Count employees by department, including departments with zero employees.
13. Calculate conditional counts for active, inactive and pending records in one query.
14. Find the second-highest distinct salary and explain how ties affect the answer.
15. Find the top three salaries per department.
16. Find the latest transaction per account.
17. Find customers who have placed orders but no successful payments.
18. Calculate daily totals and a seven-day rolling average.
19. Find duplicate business keys and safely identify rows to retain.
20. Explain when a window function is better than GROUP BY.

## C. Indexes and query plans
21. What is a B-tree index? Which operators can it support?
22. How does a composite index work, and why does column order matter?
23. Why might PostgreSQL choose a sequential scan even when an index exists?
24. Explain nested loop, hash join and merge join at a high level.
25. What do cost, rows, actual time and loops mean in EXPLAIN ANALYZE?
26. What does BUFFERS tell you?
27. What is selectivity? How can stale statistics mislead the planner?
28. What makes a predicate non-sargable?
29. When would you use a partial, expression, GIN or BRIN index?
30. Why can adding indexes make writes slower?

## D. Transactions and concurrency
31. Explain MVCC and snapshots.
32. Compare Read Committed, Repeatable Read and Serializable in PostgreSQL.
33. What is a lost update? Show a safe update strategy.
34. What does SELECT FOR UPDATE lock, and until when?
35. How do deadlocks happen? How do you prevent them?
36. Why should a transaction be short?
37. How can long-running transactions affect vacuum and table bloat?
38. How should an application retry a serialization failure or deadlock?
39. Optimistic version check vs pessimistic row lock?
40. What is the difference between a lock wait and a slow query?

## E. PostgreSQL and application integration
41. What is the difference between JSON and JSONB?
42. Explain INSERT ... ON CONFLICT and RETURNING.
43. Why use a connection pool? What happens if the pool is undersized or oversized?
44. How do you paginate a large table? Compare OFFSET and keyset pagination.
45. What is partition pruning?
46. What is a materialized view, and how do you reason about freshness?
47. How do you safely add a NOT NULL column to a large production table?
48. How do temporary tables interact with database sessions and pooled connections?

## F. Practical query challenges
49. Given orders and order_items, calculate revenue per customer without double-counting.
50. Given events, find users with three consecutive active days.
51. Given a 7-million-row table, a slow filter and a multi-table join, explain your investigation from query correctness through EXPLAIN ANALYZE and indexing.
52. Two transactions transfer money between accounts in opposite directions. How can deterministic lock ordering prevent a deadlock?

## Interview execution checklist
State the required result first. Explain NULL and duplicate behavior. Write a correct query. Then discuss indexes, cardinality and the execution plan. Never claim a join type or SQL rewrite is universally faster without evidence.
