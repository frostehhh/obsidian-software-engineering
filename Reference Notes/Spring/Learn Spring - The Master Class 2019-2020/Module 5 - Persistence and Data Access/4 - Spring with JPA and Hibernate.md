---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-4-spring-with-jpa-and-hibernate
Draft: false
---

- Purpose of this lesson is to learn how to manually implement JPA and Hibernate without reliance on Spring Data dependency for automatically creating the repository method implementations.

# Dependencies Used
H2
HIBERNate
spring-orm


> [!NOTE]
> Hibernate is used as a dependency, but it is not explicitly used in the flow since Spring Boot already integrates with it implicitly with default configurations.

# Flow Demonstrated
1. Declare `IProjectRepository` interface for defining methods to include.
	- This is to be imported when needed for dependency injection
2. Declare `ProjectRepositoryImpl` class to include actual custom implementations
## ProjectRepositoryImpl
```java
import javax.persistence.EntityManager;  
import javax.persistence.PersistenceContext;

@PersistenceContext
private EntityManager entityManager;
```
- This contains the API needed for manipulating entities
- `@PersistenceContext` annotation is declared for Spring Boot to auto-inject the `EntityManager`

> [!note]
> `javax.persistence` is the Java eXtension package for JPA


```java
@Transactional  
@Override  
public Optional<Project> findById(Long id) {  
    Project entity = entityManager.find(Project.class, id);  
    return Optional.ofNullable(entity);  
}  

@Transactional  
@Override  
public Project save(Project project) {  
    entityManager.persist(project);  
    return project;  
}
```


# Questions
- What is the reference for overriding the DataSource?
- Why use @Transactional annotation in the examples?
	- Will be discussed in a later lesson. No need to expand here.