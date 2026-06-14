Unit IV: Intermediate and Advanced SQL

4.1 Join Expressions

Joins combine rows from two or more tables based on a related column.


INNER JOIN – returns only matching rows from both tables
LEFT JOIN – all rows from left table + matching rows from right
RIGHT JOIN – all rows from right table + matching rows from left
FULL OUTER JOIN – all rows from both tables
NATURAL JOIN – automatically joins on columns with the same name
CROSS JOIN – every combination of rows from both tables


4.2 Views

A view is a virtual table created from a SELECT query. It doesn't store data itself.


Simplifies complex queries
Provides security by hiding sensitive columns
Created with CREATE VIEW viewname AS SELECT ...
A materialized view stores the result physically for better performance


4.3 Transactions

A transaction is a sequence of SQL operations treated as one unit. Must follow ACID properties.


COMMIT – saves all changes permanently
ROLLBACK – undoes all changes since the last commit
SAVEPOINT – sets a point you can roll back to within a transaction


4.4 Integrity Constraints

Rules that ensure accuracy and validity of data:


NOT NULL – column cannot be empty
UNIQUE – all values in column must be different
PRIMARY KEY – unique + not null identifier
FOREIGN KEY – links to primary key in another table
CHECK – value must meet a condition (e.g. Age > 0)
DEFAULT – sets a default value if none is provided


4.5 SQL Data Types and Schemas

Common data types:


INT, FLOAT, DECIMAL – numbers
VARCHAR(n), CHAR(n) – text
DATE, TIME, TIMESTAMP – date and time
BOOLEAN – true/false
BLOB – binary data (images, files)


A schema is a named container that groups related tables and objects within a database.

4.6 Index Definition in SQL

Indexes speed up data retrieval.

sqlCREATE INDEX idx_name ON Student(Name);
DROP INDEX idx_name;

Unique index ensures no duplicate values in a column. Too many indexes slow down INSERT/UPDATE/DELETE.

4.7 Authorization

Controls who can do what in the database.


GRANT SELECT ON Student TO user1; – give permission
REVOKE SELECT ON Student FROM user1; – remove permission
Privileges include: SELECT, INSERT, UPDATE, DELETE, ALL
Roles group privileges together and can be assigned to users


4.8 Accessing SQL from a Programming Language

SQL can be embedded into programming languages:


Embedded SQL – SQL written directly inside host language code
JDBC (Java) / ODBC (general) – APIs that let programs connect to and query databases
Prepared statements – precompiled SQL queries, faster and safer (prevents SQL injection)


4.9 Functions and Stored Procedures


Function – returns a value, can be used in SELECT queries
Stored Procedure – a block of SQL saved in the DB and executed with CALL
Benefits: reusable code, better performance, reduced network traffic


sqlCREATE PROCEDURE GetStudent(IN id INT) BEGIN SELECT * FROM Student WHERE StudentID = id; END;

4.10 Triggers

A trigger automatically executes when a specific event occurs on a table (INSERT, UPDATE, DELETE).


BEFORE trigger – runs before the operation
AFTER trigger – runs after the operation
Used for auditing, enforcing rules, or automatic updates


sqlCREATE TRIGGER before_insert BEFORE INSERT ON Student FOR EACH ROW ...;

4.11 Recursive Queries

Used to query hierarchical or recursive data (e.g. org charts, categories).
Uses a Common Table Expression (CTE) with the WITH RECURSIVE clause:

sqlWITH RECURSIVE cte AS (
  SELECT ... -- base case
  UNION ALL
  SELECT ... FROM cte -- recursive step
)
SELECT * FROM cte;

4.12 Advanced Aggregation Features


ROLLUP – produces subtotals and grand totals
CUBE – produces subtotals for all combinations of columns
GROUPING SETS – specify exactly which groupings you want
Window functions – perform calculations across a set of rows related to the current row without collapsing them

RANK(), ROW_NUMBER(), DENSE_RANK()
SUM() OVER (PARTITION BY ...) – running totals per group