---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-3-controllers-and-urls-the-pathvariable-annotation-text-only
Draft: false
---

# @PathVariable annotation
- method parameter
- binds method parameter to path param in URL
- Can use regex
- Can mark as optional

```java
@PathVariable("id") String id;
@PathVariable(required = false) String id;
```