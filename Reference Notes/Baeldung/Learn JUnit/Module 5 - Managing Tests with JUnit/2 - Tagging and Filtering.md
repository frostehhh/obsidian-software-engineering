---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-2-tagging-and-filtering
Draft: false
---

- `@Tag` annotation
	- method level
	- Accepts single String value
- Can create custom annotation to simplify adding of tags
- When running test commands, can filter to run certain tags with `-Dgroups` option
```plaintext
mvn test -Dgroups=campaigns
```

# See also
https://www.baeldung.com/java-custom-annotation