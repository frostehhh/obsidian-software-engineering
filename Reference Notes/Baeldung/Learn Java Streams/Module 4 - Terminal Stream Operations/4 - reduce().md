---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-4-reduce
Draft: true
---

- `Stream.reduce()`
- For processing a stream into a single result

# Example
```java
.reduce((n1, n2) -> n1 + n2));

// with identity element(starting element)
.reduce(0, (n1, n2) -> n1 + n2));

// with combiner function
BigInteger product = Stream.of(1, 2, 3)
	.reduce(
		BigInteger.ONE,
		(bigInt, nr) -> bigInt.multiply(BigInteger.valueOf(nr)),
		(bigInt1, bigInt2) -> bigInt1.multiply(bigInt2)
	);

```

