Unit V: Relational Database Design

5.1 Features of Good Relational Design

Minimal redundancy – same fact not stored twice
No update, insertion, or deletion anomalies
Lossless-join decomposition – original relation recoverable by joining decomposed parts
Dependency preservation – constraints enforceable without expensive joins

5.2 Decomposition Using Functional Dependencies

Splitting a relation into smaller ones to remove redundancy.

Lossless join – joining decomposed tables gives back the exact original
Dependency preservation – FDs still enforceable on decomposed tables
A decomposition of R(A,B,C) with A→B into R1(A,B) and R2(A,C) is lossless if common attributes determine all attributes of one side

5.3 Normal Forms

1NF – Every attribute must contain atomic (single) values. No repeating groups or multi-valued cells.

2NF – Must be in 1NF + no partial dependency. Every non-key attribute must depend on the whole primary key (matters when key is composite).

3NF – Must be in 2NF + no transitive dependency. Non-key attributes must depend only on the key, not on other non-key attributes.

BCNF – Stronger than 3NF. Every determinant must be a superkey. May not always preserve dependencies.

4NF – No multivalued dependencies (X →→ Y) unless X is a superkey.

5NF – No join dependencies that aren't implied by candidate keys.

5.4 Functional Dependency Theory

If X → Y, then whenever two rows agree on X they must agree on Y.

Armstrong's Axioms: Reflexivity, Augmentation, Transitivity
Attribute closure (X+) – all attributes determined by X
Canonical cover – minimal equivalent set of FDs with no redundancy

5.5 Algorithms for Decomposition

BCNF decomposition – if X→Y violates BCNF, split into R1(X∪Y) and R2(R−(Y−X)). Lossless but may lose dependencies.
3NF synthesis – compute canonical cover, create table for each FD, add candidate key if missing. Guarantees lossless join + dependency preservation.

5.6 Multivalued Dependencies

X →→ Y means X determines a set of Y values, independent of other attributes. Leads to 4NF. Example: Student →→ Hobby and Student →→ Language.

5.7 More Normal Forms

5NF/PJNF – handles join dependencies
DKNF – every constraint follows from domain and key constraints (mostly theoretical)

5.8 Atomic Domains and 1NF

Atomic domain = values are indivisible. Columns like Phone1, Phone2, Phone3 or comma-separated values in one cell violate 1NF.

5.9 Database Design Process

Requirements → Conceptual design (ER) → Logical design (relational schema) → Schema refinement (normalisation) → Physical design → Security and application design. Design is iterative.

5.10 Modelling Temporal Data

Valid time – when a fact is true in the real world
Transaction time – when a fact is stored in the DB
Bitemporal – both valid and transaction time stored
Common approach: add start_date and end_date columns to track history
