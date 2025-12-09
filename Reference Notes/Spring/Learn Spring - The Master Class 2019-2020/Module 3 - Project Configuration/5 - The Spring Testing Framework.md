---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-5-the-spring-testing-framework-part-2
---

 - `@SpringJUnitConfig` - class annotation
 - `@Test` - method annotation

```java
@SpringJUnitConfig(value = TestConfig.class)
class ContextIntegrationTest {
}

@Configuration
@ComponentScan("com.baeldung.ls")
class TestConfig {

}
```