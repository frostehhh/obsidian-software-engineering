---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-1-repeating-tests
Draft: false
---

- `@RepeatedTest` annotation
- Repeats a test `n` amount of times
- Can have custom display name
- can have failure threshhold to indicate max number of failures to stop at 
# Purpose
- flaky tests
- testing idempotency
- testing caching
- testing intermittent issues

# Examples
## With custom display name
```java
@RepeatedTest(value = 5, name = "Test run {currentRepetition}/{totalRepetitions}")
void whenSavingCampaignRepeatedly_thenShouldAssignIdsWithRepetitionInfo(RepetitionInfo repetitionInfo) {

    System.out.println("Running repetition " + repetitionInfo.getCurrentRepetition() + " of " + repetitionInfo.getTotalRepetitions());
    // actual test logic here
}
```

## With failure threshold
```java
@RepeatedTest(value = 10, failureThreshold = 2)
void whenSavingCampaignRepeatedly_thenShouldAssignIdsWithFailureThreshold(RepetitionInfo repetitionInfo) {
    InMemoryCampaignRepository repository = new InMemoryCampaignRepository();
    Campaign campaign = new Campaign("TEST-CODE", "Test Campaign", "Repeated test scenario");
    Campaign savedCampaign = repository.save(campaign);
    if (repetitionInfo.getCurrentRepetition() % 2 == 0) {
        Assertions.fail("This repetition is a flaky one!");
    } else {
        Assertions.assertNotNull(savedCampaign.getId(),
                "Campaign ID should be assigned in repeated test");
    }
}
```