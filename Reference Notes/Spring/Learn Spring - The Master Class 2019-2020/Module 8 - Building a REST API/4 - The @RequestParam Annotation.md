---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-4-controllers-and-urls-the-requestparam-annotation-text-only
Draft: true
---

# @RequestParam
- method parameter
- binds method parameter to query param in URL
- Can mark as optional

```java
@RequestParam(name = "name") String name;

// optional
@RequestParam(name = "name", required = false) String name;
@RequestParam(name = "name") Optional<String> name;

@RequestParam(name = "name", defaultValue = "") String name;
```

