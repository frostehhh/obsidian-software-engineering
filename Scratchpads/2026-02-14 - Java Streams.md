---
date: "2026-02-14T20:15"
related::
- "[[1 - Functional Programming and Java Streams]]"
- "[[2 - Functional Interfaces and Lambdas in Java]]"
---

# Streams
- A solution for simplifying complex transformations of collections in Java
- Can include multiple transformations(ex. filter, sort, map in a single stream)
- Hides overhead of defining loops
- Clearer intent on purpose of code 
- May be difficult to debug streams via breakpoints and debugger
- May be unnecessary for simple modifications
# Lambda Functions and Functional Interfaces


```java
@FunctionalInterface
interface CustomFunction {
	@Override
	void apply(String name) {
		println(name)
	}
}
```

- Must have 1 abstract method
- `@FunctionalInterface` annotation is merely for clarify intent via IDE that this is a functional interface
- 