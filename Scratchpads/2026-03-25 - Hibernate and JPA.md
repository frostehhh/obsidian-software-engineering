---
date: 2026-03-25T22:02
Draft: true
tags:
  - java/hibernate
  - java/jpa
---

# Outline
Module 2 - lesson 3 to end
Module 3 - lesson 1
- Module 2
	- enum
	- date
	- advanced id
	- inheritance
- Module 3
	- CRUD


# Module 2
## Enum
- uses an enum annotation
- default is CARDINAL type which is like 0, 1, 2, 3, 4, if the enum annotation is not specified
## Date 

## Advanced ID
- @Embeddable - annotation attached to a class that can be embedded
	- Allows creation of composite keys in classes
- @EmbeddedId - mark a entity class method as an embeddedId. The type must be referencing a class annotated with @Embeddable
- @NaturalId can be annotated on natural IDs. This optimizes lookup for this fields
# Inheritance
- Types
	- Single Table
	- Class per table
	- Join as table
	- mapped superclass - no table

## SingleTable
- A single database table can result to 2 or more different classes via inheritance
- This is decided via a discriminator column that dictates the class it should be shaped into

## Table by Class
- 1 subclass = 1 table
- This means that superclass properties and duplicated across subclass tables

# Join as table
- 1 parent table that contains common attributes
- Sub class tables contain only attributes that are specific to that subclass

## Mapped superclass
- does not have a reference table
- the inheritance is implemented only via class
- How is the class implemented?
- Similar to table by class but without separate tables
	- subclass = 1 column
- The issue with this is that polymorphic queries are not supported
- 