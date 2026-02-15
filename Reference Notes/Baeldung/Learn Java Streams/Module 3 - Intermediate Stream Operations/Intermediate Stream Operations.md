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
> [!question] Multiple map() vs combined map()?
> It is possible to write multiple consecutive `map()` calls. The benefit of this can be for readability's sake. The performance impact is negligible especially for simple operations where in most cases, you can opt for readability via multiple `map()` callls
> https://stackoverflow.com/questions/35048130/java-8-stream-string-of-map-calls-versus-combining-into-one

- `sorted()` - for sorting
	- Can use `Comparator` or `Comparable` interfaces
- `distinct()` - for filtering to include unique elements only based on the [[equals()]] and [[hashCode()]] implementation used
- `skip()` - skip `n` number of elements
- `limit()` - limit max number of elements returned by the stream by `n`
> [!note]
> Pagination can be implemented by using both `skip()` and `limit()`. Note that `skip()` must always be used before `limit()`
- `peek()` 
	- read each element in the stream without modification. Although it is possible to modify, it goes against the purpose of this method
	- Can be used for logging. In case of multiple logs, consider using a higher log level such as `VERBOSE` to limit when these logs are shown 