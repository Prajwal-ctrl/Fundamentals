# PostgreSQL & SQL Learning Roadmap

This folder tracks SQL fundamentals and PostgreSQL behavior, with a focus on writing correct queries first and then understanding their execution and performance.

## 1. Relational database fundamentals
- Tables, rows, columns and relations
- Primary keys, foreign keys and constraints
- NULL semantics
- Data types and type casting
- Normalization basics
- Referential integrity

## 2. SQL query fundamentals
- SELECT, INSERT, UPDATE and DELETE
- WHERE and boolean logic
- IN, BETWEEN, LIKE and pattern matching
- ORDER BY and LIMIT/OFFSET
- DISTINCT
- NULL checks and COALESCE
- CASE expressions

## 3. Joins
- INNER JOIN
- LEFT JOIN and RIGHT JOIN
- FULL OUTER JOIN
- CROSS JOIN
- Self joins
- Multi-table joins
- Join predicates in ON vs filters in WHERE
- NULL behavior and unmatched rows
- Join cardinality and duplicate multiplication
- Choosing joins based on required results
- Reading join algorithms in EXPLAIN plans

## 4. Aggregation and grouping
- COUNT, SUM, AVG, MIN and MAX
- GROUP BY and HAVING
- Aggregate FILTER clause
- Conditional aggregation with CASE
- DISTINCT aggregates
- Aggregation across joins
- Grouping sets, ROLLUP and CUBE
- Common aggregation mistakes and NULL handling

## 5. Subqueries and CTEs
- Scalar and table subqueries
- IN, EXISTS and NOT EXISTS
- Correlated subqueries
- Common Table Expressions (WITH)
- Recursive CTEs
- CTE materialization and inlining behavior
- Rewriting queries and comparing plans

## 6. Window functions
- OVER and PARTITION BY
- ORDER BY and window frames
- ROW_NUMBER, RANK and DENSE_RANK
- LAG and LEAD
- Running totals and moving averages
- First/last value and ranking problems
- Window functions vs GROUP BY

## 7. Indexes
- B-tree indexes
- Composite and covering indexes
- Partial and expression indexes
- GIN, GiST and BRIN overview
- Selectivity and index statistics
- Index-only scans and visibility map
- Write overhead and index maintenance
- Choosing indexes from query patterns

## 8. Query planning and optimization
- PostgreSQL planner and executor
- EXPLAIN and EXPLAIN ANALYZE
- BUFFERS and I/O interpretation
- Sequential, index and bitmap scans
- Nested loop, hash and merge joins
- Cardinality estimates and statistics
- Sorting, hashing and memory
- Query rewrites and benchmarking
- Prepared statements and plan behavior

## 9. Transactions and concurrency
- ACID properties
- MVCC and snapshots
- Transaction isolation levels
- Row-level and table-level locks
- SELECT FOR UPDATE and FOR SHARE
- Deadlocks and lock ordering
- Optimistic concurrency patterns
- Vacuum and autovacuum
- Long-running transactions

## 10. PostgreSQL application engineering
- JSON and JSONB
- Functions and procedures
- PL/pgSQL fundamentals
- Temporary tables
- Sequences and identity columns
- Partitioning
- Materialized views
- Connection pooling
- Migrations and schema evolution

## Practice and documentation convention
Each topic gets its own Markdown file with:
1. Problem and intended result
2. Schema and sample data
3. Query examples and expected output
4. Basic, intermediate and complex exercises
5. Correctness notes, especially NULL and duplicate behavior
6. Execution-plan analysis where performance is discussed
7. Alternative query forms and trade-offs
8. Official PostgreSQL references

## Performance rule
Never claim INNER JOIN is inherently faster than LEFT JOIN. Choose the join that expresses the required result, then inspect the actual plan and benchmark representative data. Use EXPLAIN (ANALYZE, BUFFERS) when measuring execution behavior.

---

## 🔴 Interview-focused additions for a 2–3 YOE backend developer

The red marker 🔴 identifies high-priority additions. SQL interviews often test whether you can predict the exact rows returned—not merely remember join definitions.

### 🔴 11. SQL correctness and tricky edge cases
- Three-valued logic: TRUE, FALSE and UNKNOWN
- NULL comparisons, IS NULL and COALESCE
- COUNT(*), COUNT(column) and COUNT(DISTINCT column)
- NOT IN vs NOT EXISTS when NULL is present
- WHERE vs HAVING
- ON predicate vs WHERE predicate with LEFT JOIN
- Duplicate multiplication in one-to-many and many-to-many joins
- UNION vs UNION ALL
- DISTINCT: correctness and cost implications
- CASE expressions and conditional aggregation
- Date/time boundaries and time-zone-safe filtering

### 🔴 12. Complex query problem patterns
- Find the second / Nth highest salary with ties
- Top N records per group
- Find duplicates and remove duplicates safely
- Find missing rows using anti-joins / NOT EXISTS
- Consecutive dates and gaps-and-islands
- Running totals and rolling averages
- Latest row per customer / entity
- Conditional counts and sums across multiple categories
- Multi-table joins without inflating aggregates
- Pagination with deterministic ordering

### 🔴 13. Index and query-performance reasoning
- Composite index column order and leftmost-prefix reasoning
- Selectivity, cardinality and statistics
- When an index is not useful
- Sequential scan vs index scan vs bitmap scan
- Nested loop vs hash join vs merge join
- Sort and hash memory behavior
- Sargable predicates and avoiding unnecessary functions on indexed columns
- Partial and expression indexes
- Covering indexes and index-only scans
- EXPLAIN estimates vs EXPLAIN ANALYZE actuals
- BUFFERS, I/O and rows-removed-by-filter
- Benchmarking with representative data and warm/cold cache caveats

### 🔴 14. Transactions, locking and concurrency
- ACID and transaction boundaries
- MVCC snapshots and visibility
- Read Committed vs Repeatable Read vs Serializable
- Lost updates, non-repeatable reads and serialization failures
- SELECT FOR UPDATE / FOR NO KEY UPDATE / FOR SHARE
- Lock waits, lock ordering and deadlock prevention
- Optimistic version checks vs pessimistic locks
- Retry strategy for serialization failures and deadlocks
- Long-running transactions and vacuum impact
- Isolation behavior under concurrent sessions

### 🔴 15. PostgreSQL application engineering
- Connection pooling and maximum-connection budgeting
- Prepared statements and plan selection awareness
- JSON vs JSONB and appropriate indexes
- Upsert with INSERT ... ON CONFLICT
- RETURNING clause
- Bulk insert/update strategies
- Partition pruning and partition-key design
- Materialized view refresh and freshness trade-offs
- Function vs procedure and transaction behavior
- Temporary table lifecycle and connection/session scope
- Migrations, constraints and safe schema changes

## Interview questions and practical drills

See [Interview-Questions.md](Interview-Questions.md) for query-writing, join correctness, aggregation, window-function, indexing, execution-plan and transaction scenarios.

## Interview rule: correctness before performance

When asked "Which is faster, INNER JOIN or LEFT JOIN?", do not guess. First explain which rows the requirement demands. Then discuss whether the optimizer can transform the query, inspect the actual plan, and benchmark representative data. The same discipline applies to CTE vs subquery, EXISTS vs JOIN, and index vs sequential scan.

Official references:
- [PostgreSQL current documentation](https://www.postgresql.org/docs/current/)
- [Using EXPLAIN](https://www.postgresql.org/docs/current/using-explain.html)
- [Indexes](https://www.postgresql.org/docs/current/indexes.html)
- [Transaction isolation](https://www.postgresql.org/docs/current/transaction-iso.html)
- [Explicit locking](https://www.postgresql.org/docs/current/explicit-locking.html)
