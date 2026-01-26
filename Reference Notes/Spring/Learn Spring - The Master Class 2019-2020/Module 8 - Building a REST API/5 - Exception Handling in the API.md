---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-5-exception-handling-in-the-api-part-1
Draft: true
---

- The purpose of exception handling is for explicit and intentional control over the responses returned to the client in case of exceptions
	- We may want to avoid returning raw errors such as `Internal Server error`
- `@ControllerAdvice` annotation - makes the configuration globally available to all controllers
- `@ExceptionHandler` - specifies the exception class to handle
	- Can specify a parent exception class, which will also intercept subclasses
- `extends ResponseEntityExceptionHandler` - class provided by Spring Boot to provide defaults for framework-specific exceptions
```java
@ControllerAdvice  
public class GlobalExceptionHandler extends ResponseEntityExceptionHandler {  
  
    @ExceptionHandler(EmptyResultDataAccessException.class)  
    public ResponseEntity<String> handleEmptyResultDataAccessException(EmptyResultDataAccessException ex) {  
        return new ResponseEntity<>("Exception retrieving data: " + ex.getMessage(), HttpStatus.NOT_FOUND);  
    }  
}
```