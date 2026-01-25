---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-3-pagination-and-sorting
Draft: true
---

- `PagingAndSortingRepository<EntityClass, IdType>` for supporting pagination and sorting for repository interfaces

```java
public interface IProjectRepository extends PagingAndSortingRepository<Project, Long> {
}
```

```java
Page<Project> projects = projectRepository.findAll(PageRequest.of(0, 2));
Page<Project> projects = projectRepository.findAll(PageRequest.of(0, 2, Sort.by(Order.asc("name"))));
```