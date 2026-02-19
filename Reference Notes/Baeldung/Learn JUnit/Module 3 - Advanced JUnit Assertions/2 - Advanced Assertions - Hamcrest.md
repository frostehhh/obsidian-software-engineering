---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-2-advanced-assertions-hamcrest
Draft: false
---

- 3rd-party assertion tool to use along with JUnit
- See source_url for examples
- More descriptive assertion and test reports on errors

```java
assertThat(tasks, hasSize(2));
assertThat(tasks, containsInAnyOrder(task1, task2));

assertThat(tasks, everyItem(allOf(
    hasProperty("assignee", hasProperty("id", is(100L))),
    hasProperty("name", startsWith("BACKEND")),
    not(hasProperty("name", containsString("FRONTEND")))
)));
```

# See Also
https://hamcrest.org/JavaHamcrest/