---
tags:
  - reference-notes
  - java/junit
  - software/testing/unit
source_url: https://www.baeldung.com/members/courses/learn-junit/lessons/lesson-2-mocking
Draft: false
---

- Mocking is make a fake implementation of a component for the sake of providing data
- Example
	A test class is made for `CampaignService`. Internally, it uses `CampaignRepository`. In this case, we need to mock the `CampaignRepository` methods that are to be used
- Mockito significantly simplifies the setup needed for creating mocks. Otherwise, 

# Mockito
## Methods
`Mockito.mock()` - creates mock instance
`Mockito.when()` - When a method on a mock instance is called, define what output that method returns

```java
class CampaignServiceMockLifecycleUnitTest {
    private CampaignRepository repository;
    private DefaultCampaignService service;

    @BeforeEach
    void setup() {
        this.repository = Mockito.mock(CampaignRepository.class);
        this.service = new DefaultCampaignService(repository);
    }

    @Test
    void whenClosingACampaignWhichIsNotFound_thenReturnEmpty() {
        Mockito.when(repository.findById(1L))
          .thenReturn(Optional.empty());

        assertTrue(service.closeCampaign(1L).isEmpty());
    }

    // other tests
}

```
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