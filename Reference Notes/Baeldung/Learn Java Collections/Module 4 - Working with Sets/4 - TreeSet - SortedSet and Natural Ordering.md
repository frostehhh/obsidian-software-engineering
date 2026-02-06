---
tags:
  - reference-notes
  - java/collections/set
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-4-treeset-sorted-set-and-natural-ordering
Draft: false
---

- Based on red-black tree data structure for natural sorting of set data
- Low performance to other set implementations in terms of writing data due to tree rebalancing
- Good if you need sorted data

# Initialization
```java
TreeSet<Number> set = new TreeSet<>();
set.add(1);
set.add(5);
set.add(7);
```