---
tags:
  - reference-notes
  - java/streams
source_url: https://www.baeldung.com/members/courses/learn-java-streams/lessons/lesson-1-functional-programming-and-java-streams
Draft: false
---

- Java Streams are a way to simplify complex data transformations for collections

# Usage Notes and Benefits
- Simplified declaration, which clarifies the intent and the intended modification
	- If otherwise using for loops, nesting may occur and it may be very verbose depending on the complexity of the intended modifications
- Code overhead such as for loops are abstracted
- **Lazily processed**. Processed only when the value is needed
- A stream must be used only once. It is not expected to be reused. If attempted to be reused, an error `IllegalStateException` will be thrown

# Pitfalls
- **Difficulty in debugging complex streams**. It is not as easy to debug by inserting breakpoints in between operations compared to using basic iteration logic
- There may be issues if an object being processed into a stream is updated midway
- Unnecessary for very simple modifications

# Example
```java
// imperative
String joinCodesImperatively(List<Task> tasks) {  
    List<String> codes = new ArrayList<>();  
    tasks.forEach(t -> {  
        if (t.getCode().startsWith("T")) {  
            codes.add(t.getCode());  
        }  
    });  
    return String.join(", ", codes);  
}

// with streams
String joinCodesWithStream(List<Task> tasks) {  
    return tasks.stream()  
        .map(Task::getCode)  
        .filter(code -> code.startsWith("T"))  
        .collect(Collectors.joining(", "));  
}
```