---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-3-functional-interfaces-and-lambdas-in-java
Draft: false
---

# Functional Interfaces
An interface that implements exactly one abstract method

```java
Function<String, Integer> getLength = new Function<>() {
	@Override
    public Integer apply(String s) {
        return s.length();
    }
}
```

- Can add a `@FunctionalInterface` annotation to notify intent that this must only have one abstract method
- Variables used from outside of the scope of a function must be effectively final. Either
	- final
	- declared once and never reassigned

## Built-in Functional Interfaces
- Consumer
- Supplier
- Function
- BiFunction
- Predicate
# Lambda Expressions
- Shorthand for [[#Functional Interfaces]]
- Helps to avoid need to declare verbose functional interfaces, which may be difficult to read in more complex cases
- For methods that expect `Function` or other functional interfaces, we can assign a lambda expression to them
# See Also
https://www.baeldung.com/java-effectively-final