---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-1-entity-mappings-2
Draft: false
---

This chapter focuses on annotations for mapping classes and columns to a  [[Data Definition Language]]

# Annotations
- `@Entity` mapping a class as an entity in a database
	- Can override entity name(aka class name) via `@Entity(name = "SampleName")`
- `@Table`
	- By default, a class marked as an entity uses the Entity name as the Table name
	- This annotation can be used to override the table name like `@Table(name = "TestName")`
- `@Column` column definition
	- can be used to override column properties like name, unique, etc.
- `@Id`  used to mark a primary key value in a class field
	- Flexible in terms of data types expected
- `@GeneratedValue` defines a field to be an auto-generated value