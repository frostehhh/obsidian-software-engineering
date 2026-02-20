---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-4-conditional-test-execution
Draft: false
---

- Run tests at compile time based on certain checks
	- system property
	- environment variable
	- operating system
	- custom check
# Annotations
- `@EnabledOnOs`
- `@EnabledOnJre`
- `@EnabledIfEnvironmentVariable`
- `@DisabledIfSystemProperty`
- `@EnabledIf`

```java
@Test
@EnabledIf("isWeekend")
void givenExistingCampaign_whenFindByNonExistingId_thenNoCampaignRetrieved() {
    // ...
}

boolean isWeekend() {
    DayOfWeek today = LocalDate.now().getDayOfWeek();
    return today == DayOfWeek.SATURDAY || today == DayOfWeek.SUNDAY;
}
```