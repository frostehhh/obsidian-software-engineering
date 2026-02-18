---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-3-infinite-streams
Draft: false
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

# Stream.generate()
- Creates a stream that supplies a new value given a supplier function
# Terminating Infinite Streams
- Note that these streams are not intended to run indefinitely. Need to explicitly terminate them to free resources used
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

# Usecases
- Use when
	- Need to work with large amount of data

