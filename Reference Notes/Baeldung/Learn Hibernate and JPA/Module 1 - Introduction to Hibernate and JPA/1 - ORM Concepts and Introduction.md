---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-1-orm-concepts-and-introduction
Draft: false
---

# Object-relational impedance mismatch
- the problem origin
- There is an issue between the differentiating qualities between object-oriented programming vs relational databases

## Mismatches
1. Granularity
	In Java, objects can have deeply nested references to other objects. In relational databases, there is such direct mapping since there are only tables and columns. Columns can't be used to represent the deep nesting offered in OOP
2. Inheritance
	Exists in OOP, but not in relational
3. Identity
	In Java, equivalent to [[equals()]] and [[hashCode()]]
	In relational databases, this is equivalent to the primary key
4. Associations
	In Java, this can be done via object references
	In SQL, this can be done via foreign keys
5. Data Navigation
	In Java, this can be done via object references
	In SQL, this can be done via table joins.
# ORM
- is a concept that solves the object-relational impedance mismatch problem and provides a bridge between OOP and relational databases
- It is a means of mapping objects between the 2 domains considering the difference of their nature
# JPA
- [[Java Persistence API|JPA]] is a spec that standardizes how [[ORM]] frameworks should be made.
- For an ORM vendor to be JPA-compliant, they must follow JPA specs. JPA specs suggest the use of annotations to bridge OOP with relational databases ^949648

# See also
[[Hibernate]]


