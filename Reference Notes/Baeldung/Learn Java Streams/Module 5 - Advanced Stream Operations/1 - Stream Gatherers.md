---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-1-stream-gatherers
Draft: false
---

- An intermediate operation for streams that provide localized and stateful transformations
- Runs only in a single thread. Not recommended for parallel usage
- `Gatherer` interface
- `Gatherers` class for utility methods
- Can create custom `Gatherer` implementation
# Methods
1. `Gatherers.windowFixed(int)`
2. `Gatherers.windowSliding(int)`
3. `Gatherers.scan(...)`

# See Also
[Java 24 - Stream Gatherers](https://docs.oracle.com/en/java/javase/24/core/stream-gatherers.html#GUID-FE89C89E-38F4-49A0-8663-3EEC1BB9DAA0)
