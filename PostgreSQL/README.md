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