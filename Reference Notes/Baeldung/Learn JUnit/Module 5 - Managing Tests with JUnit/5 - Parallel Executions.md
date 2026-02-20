---
tags:
  - reference-notes
  - java/junit
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-5-parallel-execution
Draft: false
---

# Enabling Parallel Tests
- In `/test/resources/junit-platform.properties`, add 
	- `junit.jupiter.execution.parallel.enabled=true`
- Add the execution method via any of the following methods
	- Include the property value for it: `junit.jupiter.execution.parallel.mode.default = concurrent`
	- Annotate a class with `@Execution(ExecutionMode.CONCURRENT)`

# Specifying Resource locks
- Resource locks are necessary in case multiple tests modify the same resource
- `@ResourceLock("lock-name")` annotation

# See also
https://docs.junit.org/6.0.3/writing-tests/parallel-execution.html