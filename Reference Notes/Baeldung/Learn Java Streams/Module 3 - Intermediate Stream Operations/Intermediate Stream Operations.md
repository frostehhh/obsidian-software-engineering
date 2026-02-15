---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-1-filter
Draft: true
---

- `filter()` - given a `Predicate`, removes entries that are `false`
- `map()` - transforms each item
- `flatMap()` - adds the results from the returned stream into the parent stream
- 


> [!question] Multiple map() vs combined map()?
> It is possible to write multiple consecutive `map()` calls. The benefit of this can be for readability's sake. The performance impact is negligible especially for simple operations where in most cases, you can opt for readability via multiple `map()` callls
> https://stackoverflow.com/questions/35048130/java-8-stream-string-of-map-calls-versus-combining-into-one

