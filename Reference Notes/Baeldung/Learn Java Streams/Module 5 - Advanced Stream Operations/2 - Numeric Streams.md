---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-2-numeric-streams 
Draft: false
---

- Streams for number types in java
	- `IntStream`
	- `LongStream`
	- `DoubleStream`
- The benefit of this over the generic `Stream` is that it avoids the overhead of boxing and unboxing. Each numeric stream works directly with the related primitive numeric type
- Contains methods that are particular for number types including but not limited to:
	- `average()`
# Examples
```java
// creation
Stream.mapToInt(...)
IntStream.of(1,2,3,4)

// sum
IntStream.of(1,2,3).sum()

// range
IntStream.range(1, 5)
```

See source URL for more examples
