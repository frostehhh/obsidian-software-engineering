---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-2-beyond-the-default-repository
Draft: true
---

# Extending the default repository method with custom methods
The default repository can be extended with new methods with the certain specs available in Spring/Spring Boot?

**Examples**
```
Optional<Project> findByName(String name);
List<Project> findByDateCreatedBetween(LocalDate startDate, LocalDate endDate);
```


# Extending Project with 0 to many Tasks
# @Query Annotation
- `@Query`

```java
@Entity
public class Project {

    @Id
    @GeneratedValue
    private Long id;

    private String name;

    private LocalDate dateCreated;

	// A Project can have 0 or more tasks
    @OneToMany(fetch = FetchType.EAGER, cascade = CascadeType.ALL)
    @JoinColumn(name = "project_id")
    private Set<Task> tasks;
    
    // ...
}
```