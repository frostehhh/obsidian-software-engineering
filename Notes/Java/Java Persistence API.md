---
tags:
  - notes
  - java/jpa
Draft: true
aliases:
  - JPA
---

# JPA[^1]
- A specification indicating how object-relational mapping must be implemented
- Spec describes how to interact with relational databases, tables and entities
# Core Components[^1]
## Entity
- Defines a class as an entity
- `@Entity` annotation
- `@Table` to configure corresponding database table
## EntityManager
- Core API class for interacting with entities via JPA
## Persistence Context

## Criteria
API for creating dynamic queries
## JPQL
- JPA-specific SQL language
- Database agnostic

# JPA vs Hibernate[^2]
- Hibernate is an ORM library for Java
- JPA specification was created afterward based on that implementation
# References
https://www.geeksforgeeks.org/java/jpa-introduction/
https://www.infoworld.com/article/2259807/what-is-jpa-introduction-to-the-java-persistence-api.html

[^1]: https://www.geeksforgeeks.org/java/jpa-introduction/
[^2]: https://www.infoworld.com/article/2259807/what-is-jpa-introduction-to-the-java-persistence-api.html
