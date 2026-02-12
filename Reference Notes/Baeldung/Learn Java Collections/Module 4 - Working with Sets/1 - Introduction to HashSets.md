---
tags:
  - reference-notes
  - java/collections/set
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-1-introduction-to-hashset
Draft: false
---

![[Set]]
- Internally uses HashMap for indexing elements
- Implementation class of `Set` interface, which extends `Collection`

# Initializing
```java
// Basic
Set<String> set = new HashSet<>();

// size to initialize default capacity
new HashSet<>(size);
// load factor indicates how when to increase size based on current and max capacity. Accepts value from 0 - 1.
// Lower value means more memory usage
// higher value has higher chance of hash collision
// 0.75f is safe default for general purpose
new HashSet<>(size, loadFactor);
Set<String> set = new HashSet<>(size, loadFactor);

// for creating immutable sets
Set.of(1, 2)
Collections.singleton(1)
```