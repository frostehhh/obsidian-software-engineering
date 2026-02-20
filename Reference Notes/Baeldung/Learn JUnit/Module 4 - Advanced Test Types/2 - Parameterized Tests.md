---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-2-parameterized-tests
Draft: false
---

- `@ParameterizedTest` annotation
- used to run tests for each value provided by a `*Source` annotation
- For testing multiple inputs, with a single declared test method

# Source annotations
- ValueSource
- NullSource - null value
- EmptySource - empty string or empty map or empty data type based on the type
- EnumSource
- MethodSource
- CsvSource
- CsvFileSource

