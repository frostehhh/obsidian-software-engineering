---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-5-transactions-in-spring-text-only
Draft: false
---

- Create transaction via `@Transaction` annotation
- Rollbacks changes on catch of any unchecked exception
- Changes are committed in case of checked exception
- Can be used to annotate class or method
- Ensures that all actions in a method either succeed or fail at the same time

# Under the hood
- Spring relies on AOP proxies to insert transactional logic on method calls
- The proxying infrastructure only intercepts external method calls
	- if an object's method calls another method annotated with `@Transactional` in the same object, the proxying infrastructure will not intercept this method call. Thus, transactional logic will not be inserted.
# See Also
[[Database Transaction|Transaction]]