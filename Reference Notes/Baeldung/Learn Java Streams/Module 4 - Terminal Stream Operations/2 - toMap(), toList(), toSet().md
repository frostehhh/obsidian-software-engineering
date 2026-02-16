---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-2-tomap-tolist-toset
Draft: true
has-questions: true
---

# toList()
- `.collect(Collectors.toList())` - creates mutable list
- `.collect(Collectors.toUnmodifiableList())` - immutable list
- `Stream.toList()` - immutable list

# toMap()
```java
.collect(Collectors.toMap(Task::getCode, Task::getName))

// with merger function
.collect(Collectors.toMap(Task::getCode, Task::getName, (t1, t2) -> t1 + ", " + t2))


```

# toSet()
- `.collect(Collectors.toSet())` - creates mutable set
- `.collect(Collectors.toUnmodifiableSet())` - immutable set
- `Stream.toSet()` - immutable set

# Collectors.toCollection()
- Allows to specify custom implementation of class to mutate results to 
```java
.collect(Collectors.toCollection(LinkedList::new))
```
# Questions
