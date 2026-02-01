---
tags:
  - reference-notes
  - java/collections
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-3-working-with-arrays
Draft: false
---

# Array Structure
# Creating Arrays
```java
int[] myArr = new int[5];
int[] myArr2 = new int[5] {1, 2, 4, 5, 3};
```

# Accessing Array Values

```java
myArr[4] // 3
```

# Iterating Arrays
```java
for (int i = 0; i < myArr.length; i++) {
	myArr[i];
}
```