---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-2-working-with-profiles-in-spring-2
Draft: false
---

- @Profile annotation 
	- Can be used for both classes and methods
	```java
	@Profile("dev")
	```
- in `application.properties`
```
spring.profiles.active=dev
// for multiple profiles
spring.profiles.active=dev,qa
```