---
tags:
  - reference-notes
  - low-level-design
  - design-patterns
source_url: https://www.hellointerview.com/learn/low-level-design/in-a-hurry/patterns
---

# Creational
## Factory
- A creator class responsible for creating specific types of objects
- An alternative for simplicity is simple initializing a class with a constructor
## Builder
- Simplifies building of objects via a builder class where each method builds a part of the object
- a method, which by convention can be called `build`, is included to create the object
- Example: Query builders
## Singleton
- Have a single instance of an object or value
## Examples[^1]
```java
public enum SingletonEnum {
	INSTANCE;
	
	private String value = "hehe";
	
	public String getValue() {
		return value;
	}
	
	public void setValue(String s) {
		value = s;
	}
}

SingletonEnum singleton = SingletonEnum.INSTANCE;

System.out.println(singleton.getValue());
singleton.setValue("heheeee");
System.out.println(singleton.getValue());
```
# Structural
## Decorator
- Wrap a class with another class to add new behaviors
- A higher order class
## Facade
- A container pattern
- Hide complexity and multiple behaviors behind a single class abstraction
# Behavioral
## Strategy
- OOP for `if...else if... else`/`switch`
## Observer
- When a value changes, observers receive the update and perform the behavior specified on update
## State Machine
- Behavior of each method depends on the state
- Separate `StateMachine` class for each separate state
# References
https://dzone.com/articles/java-singletons-using-enum

[^1]: https://dzone.com/articles/java-singletons-using-enum
