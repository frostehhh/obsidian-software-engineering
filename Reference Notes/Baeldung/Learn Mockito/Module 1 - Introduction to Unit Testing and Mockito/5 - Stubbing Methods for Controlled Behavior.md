---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-5-stubbing-methods-for-controlled-behavior
Draft: false
---

# Mocks vs Stubs
Stubs - an object that provides a predefined response for a method
Mocks - an object that provides simulated behavior. This may involve the use of stubs
# Stubbing
If a method call that returns a value is not stubbed, java default values are returned: null, empty list, 0, depending on the data type
## Value is expected
Create a stub for a method call that must return a value
`when(taskRepository.findById(1L)).thenReturn(sampleTask)`
## Method has no expected return value
- Explicitly define that methods that return nothing must do nothing
- Benefits
	- It is clearly defined that nothing is expected to be returned from these methods
	- when the method is changed such that from returning nothing, it will return a value, an error will be invoked.

## Consecutive thenReturn
- This is used when a method call when invoked `n` number of times returns a different result
```java
when(taskRepository.findById(1L))
	.thenReturn(sampleTask)
	.thenReturn(sampleTask2)
	.thenReturn(sampleTask3)
```
## Argument Matchers
- if no specific value is needed, can use `any*()` argument matcher helper
- Note that you cannot mix the use of exact values and argument matchers. In this case, you exact values wrapped in `eq()` or a similar matcher
See https://site.mockito.org/javadoc/current/org/mockito/ArgumentMatchers.html for list of available ArgumentMatchers