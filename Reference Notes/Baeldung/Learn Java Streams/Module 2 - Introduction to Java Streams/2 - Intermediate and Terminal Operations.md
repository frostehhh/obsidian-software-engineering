---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-2-intermediate-and-terminal-operations
Draft: false
---

# Intermediate operations
- stream methods that modify the stream, but does not terminate it
- Lazily evaluates
- Is processed only after a terminal operation is invoked
# Terminal Operation
- Invokes processing of a stream and the intermediate operations configured 
- After this, the stream can no longer be reused
	- Create a new stream if needed to do so
- An `IllegalStateException` error is thrown if a used stream is attempted to be used


