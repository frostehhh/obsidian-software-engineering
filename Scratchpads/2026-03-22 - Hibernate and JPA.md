---
date: "2026-03-22T12:26"
related-reference-note:: 
 - "[[_note_Learn Hibernate and JPA]]"
---


- java persistence is a specification. it is not immediately implementable
- The purpose of the Object-relational model is to map objects from the OOP world to relational data(SQL)
- Vendors have to implement it
- Most popular implementation is Hibernate

# JPA Specs
## Configuration
### `persistence.xml`
- Stored in the META-INF directory
	- this is a Java practice for storing configuration for packages, classes and extensions
### Dependencies
- Requires a persistence vendor. ex. Hibernate
- Can add a persistence option as needed. ex. h2 for in-memory database and simplicity

# Hibernate
## Mapping Entities
```java
@Entity
@Entity(name = "MyName") // can override entity name
@Id // mark as primary key
@GeneratedValue // AUTO by default. Can provide other options

/* 
update table name used by entity
By default, uses entity name as table name
*/
@Table(name = "columnName")

// Use for column mapping overrides
@Column(...)

// Use for mapping a class's properties to the target DB table
@Embeddable
@Embedded
```
## Mapping Relationships
```java
@OneToOne

@OneToMany
@ManyToOne

/*
Many to Many
- via JoinTable -> does not require creating separate entity 
- via new composite entity
*/
@JoinTable()
@AttributeOverrides([
	@AttributeOverride(...)
])

// via new composite entity
class WorkerSkill {

// many WorkerSkill t
@ManyToOne
private Worker
}
```