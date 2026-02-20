---
tags:
  - reference-notes
  - java/junit
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-3-writing-tests
Draft: false
---

1. Install JUnit
2. Write tests

# Installation
- With Maven, install JUnit in pom.xml
- Can use JUnit BOM added to `<dependencyManagement>` block to align versions of different JUnit dependencies
# Creating Tests
## Via IntelliJ
### Generate from class or class methods
Right click name of class or class method -> Generate -> Test
### Notes
- Can right-click `test` directory -> Mark Directory As... -> Test Root to ensure integration with IntelliJ 
## Notes
- Annotate tests with `@Test` to mark as test method
- Use `assert*` methods to test outputs
# See also
[IntelliJ - Adding Maven dependencies](https://www.jetbrains.com/help/idea/work-with-maven-dependencies.html#generate_maven_dependency)