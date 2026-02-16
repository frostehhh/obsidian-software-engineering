---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-3-groupingby-partitioningby
Draft: true
---

# groupingBy()
- Maps to key:value
- `Map<String, List<String>`

```java
.collect(Collectors.groupingBy(Task::getStatus))
// with collector
.collect(Collectors.groupingBy(Task::getStatus, Collectors.counting()))
```

# partitioningBy()
- Maps to boolean:value
- Map<Boolean, T> accepts `Predicate<? super T> predicate`

```java
Map<Boolean, List<Task>> tasksByDueDate = 
	tasks
		.stream()
		.collect(Collectors
			.partitioningBy(task -> task.getDueDate().getYear() > 2025)
		);
List futureTasks = tasksByDueDate.get(true);
List earlierTasks = tasksByDueDate.get(false);

// Can also include a collectors function
Map<Boolean, Long> taskCountByDate = 
	tasks.stream()
      .collect(Collectors.partitioningBy(task -> task.getDueDate().getYear() > 2025,
        Collectors.counting()));
```

