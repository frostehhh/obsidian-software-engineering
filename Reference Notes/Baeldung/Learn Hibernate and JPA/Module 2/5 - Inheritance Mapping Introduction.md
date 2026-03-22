---
tags:
  - reference-notes
  - java/hibernate
  - java/jpa
source_url: https://www.baeldung.com/members/courses/learn-hibernate-and-jpa/lessons/lesson-5-inheritance-mapping-introduction
Draft: false
---

# Inheritance Mapping
- Maps inheritance to relational model
# Annotations
- `@Inheritance(...)` 
	- used to configure an entity to expect inheritance
	- uses default `SINGLE_TABLE` inheritance type
- `@DiscriminatorColumn` - used to identify the column whose values will be used to identify the inheritance class to use for each entity instance
	- If not specified, column `DTYPE`, is expected by default
	```java
	@Inheritance(strategy = InheritanceType.SINGLE_TABLE) 
	@DiscriminatorColumn(name = "worker_type")
	```
- `@DiscriminatorValue` - used to indicate the `DiscriminatorColumn` value related to the entity
	```java
	@Entity
	@DiscriminatorValue("FULL_TIME")
	public class FullTimeWorker extends Worker {
	    private double salary;
	    // ... standard getters and setters
	}
	```
# See Also
https://jakarta.ee/specifications/persistence/3.2/jakarta-persistence-spec-3.2