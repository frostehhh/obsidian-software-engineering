---
tags:
  - reference-notes
  - spring
source_url: https://courses.baeldung.com/courses/487981/lectures/9808403
---

Uses the `@Autowired` annotation for dependency injection
# Types of Injection
## Constructor
```java
public class MyClass {
	private ITest itest;

	public MyClass(ITest itest) {
		this.itest = itest;
	}
}
```

> [!important]
> For testability, this method of autowiring is the most flexible and should be the default way of dependency injection

## Setter
```java
public class MyClass {
	private ITest itest;

	@Autowired
	public void setITest(ITest itest) {
		this.itest = itest
	}
}
```
## Field
```java
public class MyClass {
	@Autowired
	private ITest itest;
}
```


# Duplicate Dependencies to Inject
- Use `@Qualifier` to determine which bean to inject when there are duplicates
- Alternatively, use `@Primary` to indicate the bean with the higher preference to be injected


# Testing with Constructor-based Dependency Injection
```java
public class ProjectServiceImplTest {
    private ProjectServiceImpl projectServiceImpl = new ProjectServiceImpl(
                                    new ProjectRepositoryImpl());

    @Test
    public void givenNewProject_thenSavedSuccess() {
        Project newProject = new Project("First Project", LocalDate.now());

        assertNotNull(projectServiceImpl.save(newProject));
    }
}
```

- With constructor-based injection, we can initialize the dependencies needed without relying on Spring
- With the other injection types(setter and field), there is no easy way to do this.
- Hence, constructor-based injection is a clear winner for testability albeit more verbose