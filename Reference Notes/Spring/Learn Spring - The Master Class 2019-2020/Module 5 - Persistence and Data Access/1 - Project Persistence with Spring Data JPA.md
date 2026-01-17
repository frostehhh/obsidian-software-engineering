---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-1-project-persistence-with-spring-data-jpa
Draft: true
---

# Dependencies Needed
- `spring-boot-data-jpa` - JPA for Spring Boot
- dependency for persistence tool to use
	- For the example, used `com.h2database`, an in-memory database
# Repository Interface
- create a repository by using `@Repository` annotation
	-  extend with `CrudRepository<EntityClass, IdType>`
# Annotations
- `@Entity`
	- `@Id` - for id value
	- `@GeneratedValue` 
- `@Repository` 
	- `extends CrudRepository<EntityClass, IdType>`

# Testing
- For testing purposes for the tutorial's sake, `findById` and `save` were tested.
- Ideally, these tests aren't needed in a practical setting