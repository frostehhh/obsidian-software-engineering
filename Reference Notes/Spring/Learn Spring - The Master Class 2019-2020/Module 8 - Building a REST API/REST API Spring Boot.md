---
tags:
  - reference-notes
  - spring
source_url: https://www.baeldung.com/members/courses/learn-spring/lessons/lesson-1-controller-basics-part-1
---

- `@RestController`
	- Combination of `@Controller` and `@ResponseBody`
- `@RequestMapping`
- `@GetMapping`
- `@PutMapping`
- `@PostMapping`
- `@DeleteMapping`
- `@RequestBody`
- `@ResponseStatus`

```java
@RestController
@RequestMapping(value = "/projects")
public class ProjectController {
	@GetMapping(value = "/{id}")
	public ProjectDto findOne(@PathVariable Long id) {
	    Project entity = projectService.findById(id).orElseThrow(() -> new ResponseStatusException(HttpStatus.NOT_FOUND));
	    return convertToDto(entity);
	}
	
	@GetMapping
	public Collection<ProjectDto> findProjects(@RequestParam("name") String name) {
	  // ...
	}

	
}
```

