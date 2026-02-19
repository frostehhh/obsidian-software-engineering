---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-4-grouping-assertions
Draft: false
---

- `assertAll` to run all assertions simultaneously
- If multiple assertions fail in the `assertAll` block, all will be displayed
	- Contrasting with no `assertAll` usage, multiple assertion errors would be visible one at a time

```java
assertAll("Asserting for campaign CA-123",
            () -> assertTrue(foundCampaign.isPresent()),
            () -> assertEquals("New Social Media Campaign", foundCampaign.get().getName()),
            () -> assertEquals("CA-999", foundCampaign.get().getCode()),
            // () -> assertEquals("Social Media Campaign", foundCampaign.get().getName()),
            // () -> assertEquals("CA-123", foundCampaign.get().getCode()),
            () -> assertFalse(foundCampaign.get().isClosed())
    );
```