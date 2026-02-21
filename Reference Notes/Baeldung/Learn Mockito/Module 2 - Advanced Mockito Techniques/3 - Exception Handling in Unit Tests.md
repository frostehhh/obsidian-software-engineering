---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-3-exception-handling-in-unit-tests
Draft: false
---

`when(...).thenThrow(...)` - throw exception on value-returning method
`doThrow(...).when(...)` - throw exception on void returning method
`assertThrows(Exception.class, () -> methodCall(...))` - verify if exception is thrown


```java
when(campaignRepository.findById(1L)).thenThrow(new IllegalStateException("DB failure"));

doThrow(new IllegalStateException("Can't delete")).when(campaignRepository).deleteById(eq(1L));

// assertThrows
assertThrows(IllegalStateException.class, () -> {
            campaignService.deleteCampaign(1L);
        });
```