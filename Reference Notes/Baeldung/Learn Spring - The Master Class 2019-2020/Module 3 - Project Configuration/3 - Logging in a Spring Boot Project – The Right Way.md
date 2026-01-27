---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-3-logging-in-a-spring-boot-project-the-right-way
---

- configurable via `logging.level.` in `application.properties` file
- Initializing logger. Can use SLF4J
	```java
	private static final Logger LOG = LoggerFactory.getLogger(ProjectServiceImpl.class);
	```