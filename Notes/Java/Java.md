---
tags:
  - notes
  - programming-languages/java
Draft: true
has-questions: true
---

- Source Code(human-readable code) -> compiled by JDK -> Bytecode(executable file/binary file)
- Java Virtual Machines(JVM) execute bytecode
# Variables
- A storage location for values
- can store different [[#Types]] of data
# Types
- int
- char
- String

# Fundamentals
- inheritance
- interfaces

# Classes
- inheritance
- constructor overriding
- class members, methods, fields
- [[Keyword Modifiers]]
- static block
- initializer block
- nested classes
	- inner
		- non-static
		- static
	- local
- polymorphism - inheritance + overriding of class methods or members
## Abstract Classes

## Record classes
- special type of class for immutable class field value usecases
```java
public record Person(string name)
```
- This can also be used as a nested class
```java
public class OuterClass {
	public static record InnerClass(int x, int y) {}
}
```
# Generics
- allows classes to have generic types that can be provided at the time of usage
- Conventions
	- V - Value
	- K - Key
- Raw type
- parameterized types
- wildcard
## Generic Methods

# Lambda Expressions

# JavaDoc

# Questions
- What is an IntFunction?
- Use cases for enum as singleton?
- abstract class vs interface
- 