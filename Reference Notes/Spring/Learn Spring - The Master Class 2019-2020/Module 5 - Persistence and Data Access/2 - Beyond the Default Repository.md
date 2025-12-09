---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-2-beyond-the-default-repository
---

- `@Query`

```java
// A Project can have 0 or more tasks

@Entity
public class Project {

    @Id
    @GeneratedValue
    private Long id;

    private String name;

    private LocalDate dateCreated;

    @OneToMany(fetch = FetchType.EAGER, cascade = CascadeType.ALL)
    @JoinColumn(name = "project_id")
    private Set<Task> tasks;
    
    // ...
}
```