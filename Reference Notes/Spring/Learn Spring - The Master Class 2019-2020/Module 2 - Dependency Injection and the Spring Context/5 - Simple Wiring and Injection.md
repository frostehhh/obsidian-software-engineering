---
tags:
  - reference-notes
  - spring
source_url: https://courses.baeldung.com/courses/487981/lectures/9808403
---


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