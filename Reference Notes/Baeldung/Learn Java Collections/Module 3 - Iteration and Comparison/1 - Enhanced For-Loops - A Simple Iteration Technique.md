---
tags:
  - reference-notes
  - java/collections
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-1-enhanced-for-loops-a-simple-iteration-technique
Draft: false
---

```java
for(String name: names) {
	name
}
```

# Pros
- simpler syntax
- less boilerplate code
# Cons
- lack of accessible index
- forward-only iteration
- cannot modify during loop(can be done with traditional for loop)
