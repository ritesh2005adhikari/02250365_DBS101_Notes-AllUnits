Unit III: Introduction to SQL

3.1 Overview of SQL

SQL (Structured Query Language) is the standard language for relational databases. Divided into DDL, DML, and DQL.

3.2 SQL Data Definition (DDL)

sqlCREATE TABLE Student (StudentID INT PRIMARY KEY, Name VARCHAR(50), Age INT);
ALTER TABLE Student ADD Email VARCHAR(100);
DROP TABLE Student;

3.3 Basic SQL Query Structure

sqlSELECT column FROM table WHERE condition ORDER BY column GROUP BY column HAVING condition;

3.4 Additional Basic Operations


AND, OR, NOT – combine conditions
LIKE 'A%' – pattern matching
BETWEEN 18 AND 25 – range
IN (18, 20, 22) – membership check


3.5 Set Operations


UNION – combines results, removes duplicates
UNION ALL – keeps duplicates
INTERSECT – common rows only
EXCEPT – rows in first query but not second


3.6 Null Values

NULL = missing/unknown data. Use IS NULL or IS NOT NULL to check. Cannot use = NULL.

3.7 Aggregate Functions


COUNT(*) – count rows
SUM, AVG, MAX, MIN
Use GROUP BY to group rows
Use HAVING to filter groups


3.8 Nested Subqueries

A query inside another query. Can be used with WHERE, IN, or as correlated subqueries.

sqlSELECT Name FROM Student WHERE Age > (SELECT AVG(Age) FROM Student);

3.9 Modification of the Database

sqlINSERT INTO Student VALUES (1, 'John', 20);
UPDATE Student SET Age = 21 WHERE StudentID = 1;
DELETE FROM Student WHERE StudentID = 3;