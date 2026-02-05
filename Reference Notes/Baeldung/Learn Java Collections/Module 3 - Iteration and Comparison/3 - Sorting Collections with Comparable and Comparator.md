---
tags:
  - reference-notes
  - java/collections
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-3-sorting-collections-with-comparable-and-comparator
Draft: false
---

# Comparable
- `Comparable` interface
- implement the `int compareTo(Object obj)` method
- Suitable for natural ordering
# Comparator
- `Comparator` interface
- implement the `int compare(Object obj1, Object obj2)` method
- Suitable for more complex comparisons

```java
Comparator<Task> comparator = new Comparator<>();

@Override
public int compare(Task t1, Task t2) {
	return t1.getDate().compareTo(t2.getDate());
}
```

```java
Comparator<Task> comparator = Comparator.comparing(Task::getName)
	.thenCompare(Task::getCode)
	.reversed()
	
// can also use tasks.sort(comparator) for the same result
Collections.sort(tasks, comparator);
```

# See also
[[Method References]]