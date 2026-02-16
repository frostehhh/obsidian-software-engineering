---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-1-collect
Draft: false
---

- A terminal method for concatenating the stream results into a single output
- `Collector` interface
- `Collectors` class contains utility methods
- Can make `Collector` object via `Collectors.of()` helper
# Commonly used Collector Implementations
`Collectors`
- toList
- toMap
- toSet
- joining
- groupBy
# Examples
```java
String myStr = tasks.stream()
	.map(Task::getName)
	.collect(Collectors.join(", "));
```