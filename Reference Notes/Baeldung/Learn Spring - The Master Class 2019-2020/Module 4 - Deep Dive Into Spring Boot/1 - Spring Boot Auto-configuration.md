---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-1-spring-boot-auto-configuration
Draft: false
---

# Annotations mentioned
- ConditionalOnClass
- ConditionalOnMissingBean

```java
@Configuration @ConditionalOnClass(ObjectMapper.class) public class JacksonAutoConfiguration { // ... }
```


# Can Override Spring's Default Provided Beans
- Create a @Configuration class and provide the needed bean/s.
```java
@Configuration
class MyConfig {
	@Bean
	public ObjectMapper objectMapper() {
		return ObjectMapper()
	}
}
```
# Debug Via
- `application.properties` -> `logging.level.org.springframework.boot.autoconfigure=DEBUG`

# See Also
https://docs.spring.io/spring-boot/api/java/org/springframework/boot/autoconfigure/condition/package-summary.html