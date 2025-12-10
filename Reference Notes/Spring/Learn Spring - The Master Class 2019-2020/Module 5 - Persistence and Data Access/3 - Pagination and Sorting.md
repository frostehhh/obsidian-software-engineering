---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-3-pagination-and-sorting
---

- `PagingAndSortingRepository<EntityClass, IdType>` for supporting pagination and sorting for repository interfaces

```java
public interface IProjectRepository extends PagingAndSortingRepository<Project, Long>,
                    CrudRepository<Project, Long> {
}
```