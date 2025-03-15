---
aliases:
  - DI
---
# Dependency Injection (DI)
Dependency injection (DI) is a process where objects define their dependencies only through constructor arguments, arguments to a factory method, or properties that are set on the object instance after it is constructed or returned from a factory method[^1]

## Types of Dependency Injection
- constructor-based[^2]
	```kotlin
	package examples
	
	class ExampleBean
	@ConstructorProperties("years", "ultimateAnswer")
	constructor(val years: Int, val ultimateAnswer: String)
	```
- setter-based[^3]
	```kotlin
	class SimpleMovieLister { 
	// a late-initialized property so that the Spring container can inject a MovieFinder 
	lateinit var movieFinder: MovieFinder 
	
	// business logic that actually uses the injected MovieFinder is omitted...
	}
	```
# Dependency Configuration
- primitive values
- refs to other beans
- inner beans
	`<bean />` config that can be placed within `<property />`
- collections
	`<list/>`, `<set/>`, `<map/>`, and `<props/>`
	- collection merging - child bean inherits properties for parent bean
- Null and empty string values - null requires `<null />`. Empty string is `""
- Compound property names - example `fred.bob.sammy`

# See also 
https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html#beans-some-examples

[^1]: https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html
[^2]: https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html#beans-constructor-injection
[^3]: https://docs.spring.io/spring-framework/reference/core/beans/dependencies/factory-collaborators.html#beans-setter-injection


