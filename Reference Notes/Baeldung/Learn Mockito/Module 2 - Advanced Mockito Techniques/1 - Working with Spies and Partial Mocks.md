---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-1-working-with-spies-and-partial-mocks
Draft: false
---

- A spy is a real implementation of a class used in testing

# Creating Spies
1. `@Spy` annotation
2. `spy()` method

```java
@Spy
DefaultCampaignService campaignService;

CampaignRepository realRepository = new InMemoryCampaignRepository();
CampaignRepository spyRepository = spy(realRepository);
```

# Creating Stubs for Spies
It is possible to create stubs for a spy's method similar to [[5 - Stubbing Methods for Controlled Behavior]]

# Notes
- Use spies if you need to test the real implementation
- It is important to think whether you need mocks or the real functions in your test implementations
- If you are stubbing too many methods of a spy, it may be worth considering simplifying the implementation