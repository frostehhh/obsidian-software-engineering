---
tags:
  - reference-notes
  - java/collections
source_url: https://www.baeldung.com/members/courses/learn-java-collections
Draft: false
---

# What is an ArrayList
- `Iterable -> Collection -> SequencedCollection -> List`
- An ordered collection of elements
- modifiable
- allows duplicates
- Inserting new elements not at the end results to shifting of elements to the right
	- May be slow of operation is frequently performed
	- No shifting of elements if element is inserted at the end
- Can check length with `size()`
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
## Arrays.asList()
```java
Arrays.asList("Monday", "Tuesday", null);
```
## List.of()
- List is unmodifiable
- Does not allow `null` values
- Must create new `ArrayList` to have modifiable list