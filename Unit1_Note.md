Unit I: Introduction to Database Systems

1.1 View of Data

Three levels of abstraction:


Physical level – how data is stored on disk
Logical level – what data is stored and relationships between them
View level – shows only relevant portion to specific users


1.2 Purpose of Database Systems


Reduces data redundancy
Ensures data consistency and integrity
Supports data sharing among multiple users
Provides security and access control
Enables backup and recovery


1.3 History of Database Systems


1950s–60s – File systems (separate files per app)
1960s – Hierarchical model (tree structure, e.g. IBM IMS)
1970s – Network model (multiple parents, e.g. CODASYL)
1970s–present – Relational model (Edgar Codd, tables + SQL)
Modern – Object-oriented, NoSQL, distributed, cloud databases


1.4 Database Applications

Banking, airlines, universities, e-commerce, healthcare, telecommunications

1.5 Database Languages


DDL – defines structure (CREATE, ALTER, DROP)
DML – manipulates data (INSERT, UPDATE, DELETE, SELECT)
DCL – controls access (GRANT, REVOKE)
TCL – manages transactions (COMMIT, ROLLBACK)


1.6 Database Design


Conceptual – ER diagrams
Logical – convert to relational tables
Physical – indexing, storage structures


1.7 Database Engine

Core service that handles storage, query processing, transaction management, and concurrency control. Must follow ACID properties (Atomicity, Consistency, Isolation, Durability).

1.8 Database Architecture


1-Tier – app and DB on same machine
2-Tier – client connects directly to DB server
3-Tier – UI layer → Application layer → Database layer (most common for web apps)


1.9 Database Users


DBA – manages security, backup, performance
Application Programmers – build apps using the DB
Sophisticated Users – write complex SQL queries
End Users – use apps that access the DB