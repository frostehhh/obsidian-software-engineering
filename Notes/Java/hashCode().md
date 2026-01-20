---
tags:
  - notes
  - programming-languages/java
Draft: false
---

- value utilized but not limited to Hash data structures such as `HashMap` and `HashSet` for comparison of hash values [^1][^2]
- hashCode() can be used to complement [[equals()]]
	- See the example in [^2]
		- Compare 2 objects by hashCode
			- If not equal, objects are unequal
			- if equal, proceed to check equality with [[equals()]] method
- General mechanism[^2]
	- If two objects are equal, they must produce equal hashCode() values
	- If two objects are not equal, it is acceptable whether the hashCode() values they produce are equal or not.
		- If the hashCode values are equal, the equality check can be done via [[equals()]]

# References

[^1]: https://www.geeksforgeeks.org/java/importance-hashcode-method-java/
[^2]: https://www.geeksforgeeks.org/java/equals-hashcode-methods-java/
