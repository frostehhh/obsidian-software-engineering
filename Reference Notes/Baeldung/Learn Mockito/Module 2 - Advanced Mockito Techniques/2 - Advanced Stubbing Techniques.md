---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-2-advanced-stubbing-techniques
Draft: false
---

# thenAnswer()
- can be used to modify mocked values
- a use case would be to modify based on the provided arguments

```java
when(taskRepository.findById(any())).thenAnswer(invocation -> {
        Long id = invocation.getArgument(0);
        return switch (id.intValue()) {
            case 1 -> Optional.of(aTask("Task 1"));
            case 2 -> Optional.of(aTask("Task 2"));
            default -> Optional.empty();
        };
    });
```
# doAnswer()
- can be used to simulate side effects performed in a method that returns `void`
- gives access to the arguments passed

```java
doAnswer(invocation -> {
        Task taskArg = invocation.getArgument(0);
        taskArg.setId(null);
        return null;
    }).when(taskRepository).delete(task);

```
# Deep Stubbing
- Concise way of specifying a stub via a chain of method calls
-  Enable via this invocation : `mock(Some.class, Mockito.RETURNS_DEEP_STUBS)`
- Should be used sparingly as it hides design issues and causes brittle tests where any changes to the underlying methods used can easily cause the test to break

```java
//given
TaskRepository taskRepository = mock(TaskRepository.class, Mockito.RETURNS_DEEP_STUBS);
TaskService taskService = new DefaultTaskService(taskRepository);

when(taskRepository.getById(1L)
	.getAssignee()
	.getFirstName()
).thenReturn("John");
```

