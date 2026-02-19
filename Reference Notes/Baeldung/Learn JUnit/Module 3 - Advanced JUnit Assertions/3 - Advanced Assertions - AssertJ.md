---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-3-advanced-assertions-assertj
Draft: false
---

- 3rd-party assertion tool to use along with JUnit
- See source_url for examples
- can rely on IDE for checking available methods from `assertThat`

```java
assertThat(tasks)
  .hasSize(2)
  .allMatch(task -> task.getAssignee().getId() == 100L)
  .noneMatch(task -> task.getName().contains("FRONTEND"))
  .containsExactlyInAnyOrder(task1, task2);
```
