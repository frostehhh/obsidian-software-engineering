---
aliases:
  - IoC
  - Introduction to IoC
---
Inversion of control is a principle where in Spring context, Spring creates or instantiates the dependencies that an object needs. For example, we have a class and in the constructor, dependencies are defined. Spring initializes those dependencies for that class's use.[^1]

- The `org.springframework.context.ApplicationContext` interface represents the Spring IoC container[^2]. This is used for instantiating, configuring and assembling beans.

## Instantiating beans
	

[^1]: https://docs.spring.io/spring-framework/reference/core/beans/introduction.html
[^2]: https://docs.spring.io/spring-framework/reference/core/beans/basics.html
