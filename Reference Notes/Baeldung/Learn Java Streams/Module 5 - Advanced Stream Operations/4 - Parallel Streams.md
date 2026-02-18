---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-4-parallel-streams
Draft: false
---

- Stream that is processed using multiple threads
- Internally, uses `ForkJoinPool` for processing the parallel stream across different threads and reducing the result into the expected output given the operation
# Creation
Creation of parallel streams can be done via either
- `parallelStream` on a `Collection` object
- `parallel` on an existing `Stream`

# Controlling Number of Threads used
The number of threads can be controlled via `ForkJoinPool` configuration since it is used internally by parallel streams

# Usage Considerations
- Use if dataset is large enough to justify the benefits. Testing prior to usage is a good practice
- hash-based data structures ...
- Use only thread-safe or stateless operations in parallel streams
- Avoid using blocking operations. This can cause thread starvation due to needing a longer time to process
- If need to isolate a potentially slow operation with parallel streams, use a custom `ForkJoinPool`, which specifies the number of threads to allocate.
# See Also
[Java 25 - ForkJoinPool](https://docs.oracle.com/en/java/javase/25/docs/api/java.base/java/util/concurrent/ForkJoinPool.html)
