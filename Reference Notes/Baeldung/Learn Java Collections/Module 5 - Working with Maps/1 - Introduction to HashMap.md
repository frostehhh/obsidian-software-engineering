---
tags:
  - reference-notes
  - java/collections/map
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-1-introduction-to-hashmap
Draft: false
---

- `Map` interface
- `HashMap` class implementation
- Methods run in constant time(get, set, etc.)

# Initialization
```java
Map<String, String> map = new HashMap<>();
Map<String, String> map = new HashMap<>(initialCapacity);
Map<String, String> map = new HashMap<>(initialCapacity, loadFactor);
Map<String, String> map = new HashMap<>(Map);

Map.of(
	1, "value"
	2, "value2"
)

Map.ofEntries(
	Map.Entry(task1.getCode(), task1),
	Map.Entry(task2.getCode(), task2),
)
```