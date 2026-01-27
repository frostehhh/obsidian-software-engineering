---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-2-controllers-and-request-response-text-only
Draft: false
---

- HttpMessageConverter
- ResponseBody
- RequestBody
- ResponseStatus

# HttpMessageConverter
- An object that is responsible for
	- deserializing HTTP request data into the corresponding class
	- serializing a class into a response data

# RequestBody
- Annotation used to indicate the class that corresponds to the data expected from the request body.
- Annotation used in method parameter

```java
@PostMapping
@ResponseStatus(HttpStatus.CREATED)
public ProjectDto create(@RequestBody ProjectDto newProject) {
	Project entity = convertToEntity(newProject);
	return this.convertToDto(this.projectService.save(entity));
}
```
# ResponseBody
annotation that indicates that the object that we're retrieving should be serialized as the response body
# ResponseStatus
- Object that provides a status code and error message if any
- Can be applied to an error or a controller method

```java
// Exception classes
@ResponseStatus(code = HttpStatus.BAD_REQUEST)
class InvalidDataException extends RuntimeException {}

// controller methods
@PostMapping
@ResponseStatus(HttpStatus.CREATED)
public ProjectDto create(@RequestBody ProjectDto newProject) {
	Project entity = convertToEntity(newProject);
	return this.convertToDto(this.projectService.save(entity));
}
```