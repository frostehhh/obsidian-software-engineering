---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-2-actuators-in-boot
Draft: true
---


- Actuators are Spring Boot features
- Monitoring purpose
- Auditing, health checks, etc.
- Enabled by adding spring-boot-starter-actuator dependency
- Creates new endpoints under `/actuator`

# Example Endpoints
- `localhost:8080/actuator/info`
- `localhost:8080/actuator/health`

# Adding Accessible Info
Add information via `application.properties` with the `info` key. These information will be available under `/actuator/info`
```
info.name=Sample name
info.description=This is a sample description
```
# Configuration
- Can update the path via the following
```xml
management.endpoints.web.base-path=/monitoring
management.endpoints.web.path-mapping.info=/information
```

# See Also
https://docs.spring.io/spring-boot/reference/actuator/enabling.html
https://docs.spring.io/spring-boot/reference/actuator/endpoints.html