Unit VI: Indexing and Query Processing

6.1 Basic Concepts of Indexing

An index is a separate structure storing key values + pointers to records. Avoids full table scans.


Without index: O(n) – scan every row
With index: O(log n) – go directly to the data


6.2 Indexing Structures


Single-level index – simple list of keys and pointers
Multi-level index – index on top of index, reduces search space
B-Tree – balanced tree, data stored at all nodes
B+ Tree – most important; internal nodes store keys only, leaf nodes store data pointers and are linked. Used by MySQL, Oracle, PostgreSQL.


B+ Tree advantages: fast search O(log n), supports range queries, efficient disk access.

6.3 Ordered vs Unordered Indices


Ordered index – keys sorted; fast search and range queries, slower inserts
Unordered index (heap) – random order; fast inserts, slow search


6.4 Indexing of Temporal and Spatial Data


Temporal indexing – time-based access (e.g. salary history, patient records)
Spatial indexing – location-based access using R-trees or Quad-trees (e.g. maps, GPS)


6.5 Indexing for Search

Types of searches supported by indexes:


Exact match: Name = 'Sonam'
Range query: Age > 20
Pattern matching: Name LIKE 'S%'


Too many indexes slow down INSERT, UPDATE, DELETE operations.

6.6 Query Processing and Optimization

Steps: SQL Query → Parsing → Translation to Relational Algebra → Optimization → Execution


Parsing – checks syntax and validates table/column names
Translation – converts SQL to relational algebra
Optimization – finds the cheapest execution plan (minimise disk I/O, CPU, memory)
Execution – runs the plan and returns results


Query cost is measured mainly by disk I/O operations.

Join strategies the optimizer chooses from:


Nested Loop Join – compare each row of A with B
Hash Join – use hash table for matching
Sort-Merge Join – sort both tables then merge


The query optimizer automatically selects the lowest-cost plan.