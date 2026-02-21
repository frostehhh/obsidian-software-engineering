---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-3-exception-handling-in-unit-tests
Draft: true
---

`thenThrow(...)`
`doThrow(...)`


```java

doThrow(new IllegalStateException("Can't delete")).when(campaignRepository).deleteById(eq(1L));
```