---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-3-infinite-streams
Draft: true
---

- `Stream.iterate()`
- `Stream.generate()`
# Stream.iterate()
- Creates a stream that can infinitely create new elements and creates them only on demand
- Can specify initial value
- Need to configure how next value is calculated

```java
Stream<Integer> stream = Stream.iterate()
```

- Can limit output via any of the following
	- limiter function in `Stream.iterate()` initialization
	- `Stream.limit(int)`
	- `Stream.takeWhile(Predicate)`
	- Any short-circuiting Stream terminal operations
		- anyMatch
		- allMatch
		- noneMatch
		- findFirst
		- findAny
- Use when
	- Need to work with large amount of data
	- 
# Stream.generate()