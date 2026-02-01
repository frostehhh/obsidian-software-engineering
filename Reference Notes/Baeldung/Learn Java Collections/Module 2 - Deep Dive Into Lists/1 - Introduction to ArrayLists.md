---
tags:
  - reference-notes
  - java/collections
source_url: https://www.baeldung.com/members/courses/learn-java-collections
Draft: true
---

# What is an ArrayList
- An ordered collection of elements
- modifiable
- allows duplicates
- Inserting new elements not at the end results to shifting of elements to the right
	- May be slow of operation is frequently performed
	- No shifting of elements if element is inserted at the end
# Creating ArrayList
- Create with `new ArrayList<>()`
- Can be created with a size parameter to reserve space

Examples
```java
List<String> myList = new ArrayList<>();

// with initial size
List<String> myList = new ArrayList<>(5);

// with existing list
List<String> listOne = new ArrayList<>(5);
List<String> newList = new ArrayList<>(listOne);
```


# Creating ArrayList with utility methods
## Arrays.toList()
```java

```
## List.of()
- List is unmodifiable