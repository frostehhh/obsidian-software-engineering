---
tags:
  - reference-notes
  - java/mockito
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-mockito/lessons/lesson-4-advanced-cases
Draft: true
has-questions: false
---

> [!todo]
> cleanup


`ArgumentCaptor`
- for capturing an argument passed to a mocked method for detailed inspection

mocking constructors

when testing with 3rd-party APIs, it is possible that we may need to mock their final classes and methods 

mocking static methods - so that we can avoid side-effects caused by static methods and verify at the minimum that they are invoked

# Questions
- What's the difference with this and doAnswer?
	doAnswer is for mocking side-effects
	ArgumentCaptor is for verifying assertions

# See Also
https://site.mockito.org/javadoc/current/org/mockito/ArgumentCaptor.html
https://www.baeldung.com/mockito-argumentcaptor