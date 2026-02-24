---
date: "2026-02-24T22:55"
---

What is mockito?

Use cases of mockito

mockito key features and apis


# What is mockito?
Mockito is a mocking framework to be used alongside testing frameworks like JUnit and TestNG

stubs - predefined response of a method call
mocks - simulation of behaviors. includes but not limited to stubbing

# Mockito usage samples

```java

when().thenReturn()
doReturn().when()

when().thenAnswer()
doAnswer().when()

// test if method is invoked
verify()

// use if you need real implementation of a class instance
// optionally, can mock some methods
spy()

// for listening to object changes that is passed to a method that does not return it. Ex. repository.save()
ArgumentCaptor
```