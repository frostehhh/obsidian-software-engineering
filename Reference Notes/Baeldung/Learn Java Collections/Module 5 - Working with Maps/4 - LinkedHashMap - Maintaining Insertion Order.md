---
tags:
  - reference-notes
  - java/collections/map
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lessons-4-linkedhashmap-maintaining-insertion-order
Draft: false
---

- Maintains insertion order OR access order
- Iteration methods as indicated in [[3 - Iterating over HashMaps]] retain the order configured

```java
// use this constructor to indicate whether we want insertion order(false) or access order(true)
Map<String, Task> map = new LinkedHashMap<>(initialCapacity, loadFactor, isAccessOrder);
```
