---
tags:
  - reference-notes
  - java/junit
  - software/testing
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-2-mocking
Draft: true
---

- Mocking is make a fake implementation of a component for the sake of providing data
- Example
	A test class is made for `CampaignService`. Internally, it uses `CampaignRepository`. In this case, we need to mock the `CampaignRepository` methods that are to be used
- Mockito significantly simplifies the setup needed for creating mocks. Otherwise, 

# Mockito
## Annotations
`@ExtendWith(MockitoExtension.class)` 
- simplifies overhead needed to setting up the mocks
- internally runs `MockitoAnnotations.openMocks()`
`@Mock` - mock this instance
`@InjectMocks` - inject mocks into this instance

```java
@ExtendWith(MockitoExtension.class)  
class CampaignServiceMockLifecycleMockitoExtensionUnitTest {  
    @Mock  
    private CampaignRepository repository;  
  
    @InjectMocks  
    private DefaultCampaignService service;
```