Unit II: Database Design

2.1 Overview of the Design Process

Five stages: Requirements collection → Conceptual design → Logical design → Physical design → Implementation

2.2 Relational Modelling


Relation – a table with rows and columns
Tuple – a row
Attribute – a column
Domain – set of allowed values for an attribute
Each row must be unique; attribute values must be atomic


2.3 The ER Model

Represents real-world data using:


Entities – real-world objects (Student, Course)
Attributes – properties of entities
Relationships – associations between entities


2.4 Complex Attributes


Simple – cannot be divided (Age)
Composite – can be divided (Address → Street, City)
Multivalued – multiple values (Phone numbers)
Derived – calculated from another attribute (Age from DateOfBirth)


2.5 Mapping Cardinalities


1:1 – Person ↔ Passport
1:N – Department → Employees
N:1 – Students → Department
M:N – Students ↔ Courses


2.6 Primary Key

Uniquely identifies each record. Must be unique and not NULL.


Candidate key – possible keys that could be primary key
Composite key – primary key made of multiple attributes


2.7 Removing Redundant Attributes

Split tables to avoid repeating data. E.g. separate Student and Department tables instead of storing DeptLocation in every student row.

2.8 Reducing ER Diagrams to Relational Schemas


Entity → Table
Relationship → Foreign key or separate table
Multivalued attribute → Separate table
Weak entity → Include owner's primary key


2.9 Extended ER (EER) Features


Specialization – superclass split into subclasses (Employee → Manager, Engineer)
Generalization – subclasses merged into superclass
Inheritance – subclasses inherit superclass attributes
Categories – entity belongs to multiple sets


2.10 ER Design Issues


Attribute vs Entity (phone number: attribute or entity?)
Attribute vs Relationship
Binary vs Ternary relationships


2.11 Alternative Notations


UML Class Diagrams – classes, attributes, relationships
Crow's Foot Notation – shows cardinality with symbols
ORM – focuses on roles objects play in relationships


2.12 Other Design Aspects


Integrity constraints (PK, FK, domain)
Normalisation (1NF → BCNF)
Performance optimisation (indexing, partitioning)
Security (access control, encryption)


2.13 ACID Properties


Atomicity – all or nothing
Consistency – DB moves from one valid state to another
Isolation – transactions don't interfere with each other
Durability – committed changes are permanent