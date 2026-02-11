---
tags:
  - reference-notes
  - java/collections/map
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-3-iterating-over-hashmaps
Draft: false
---

- `Map` itself isn't iterable
- Can use these methods to iterate Map data
	- entrySet
	- keySet
	- values

# Iteration
```java
for (Map.Entry<String, Task> entry: map.entrySet()) {
	// entry
}
```

## Modifications during Iteration
- it is generally safe to modify the value during iteration
- it is unsafe to modify the key during iteration
- Removal must be done using [[2 - iterators|Iterators]]