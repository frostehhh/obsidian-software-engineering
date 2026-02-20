---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-6-verifying-interactions-with-mocks
Draft: true
---

Mockito can be used to verify that specific methods and parameter values are invoked.
# Methods
- `verify()`
	- Exam
- `times(n)`
- `never()`
- `inOrder.verify()`



```java
verify(taskRepository).findById(2L);
verify(taskRepository).findByIdAndName(2L, "myName");
verify(taskRepository, times(2)).findById(2L);
verify(taskRepository, never()).findById(2L);

inOrder.verify(taskRepository).findById(2L);
inOrder.verify(taskRepository).findById(3L);
```