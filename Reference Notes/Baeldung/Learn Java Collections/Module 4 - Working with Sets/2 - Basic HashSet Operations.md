---
tags:
  - reference-notes
  - java/collections/set
source_url: https://www.baeldung.com/members/courses/learn-java-collections/lessons/lesson-2-basic-hashset-operations
Draft: false
---

- add
- remove
- removeAll
- removeIf
- clear

> [!warning]
> It is not safe to modify the value or values the hashCode depends on in the elements of a set. 
> 
> If a value that hashCode() depends on is modified to for example `TA`, the hash used to store that object in the set does not change. It is also possible to add a new object with a value `TA` as well. This is because the hash used for the initial object is based on the initial value, not the modified one. Effectively, that element becomes "lost" in the set.


