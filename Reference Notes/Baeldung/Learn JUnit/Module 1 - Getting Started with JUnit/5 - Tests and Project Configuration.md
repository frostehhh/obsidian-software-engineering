---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-5-tests-and-project-configuration
Draft: false
---

- Maven SureFire plugin is included in the effective pom by default in maven projects
- This can be uses to run tests via `mvn surefire:test`
- `mvn test` internally invokes SureFire
- Tests are also run on `mvn install` and `mvn package` 
	- Tests are run before being packaged
- It is possible to configure the test command to specify which tests to run