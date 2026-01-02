---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring
Draft: false
---

- An annotation to configure additional sources of properties
- `@PropertySource` and `@TestPropertySource`
- Checks the `resources` directory

```java
@Configuration
@PropertySource("classpath:additional.properties")
class AppConfig {}
```