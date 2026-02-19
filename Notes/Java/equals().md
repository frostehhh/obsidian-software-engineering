---
tags:
  - notes
  - java
Draft: false
Parent:: "[[Object class]]"
---

- equals() method exists by default in the root [[Object class]]
- Default implementation is a [[Shallow Comparison]]
- Can be overridden to provide a custom equality comparison method
	- If override is provided, must also include override for [[hashCode()]]
# Example
```java
public MyClass {
	...
	
	@Override
	public boolean equals(Object c) {
		// shallow comparison
		if (c == this) {
			return true;
		}
		
		//  check if null OR check if same instance
		if (c == null || c.getClass() != this.getClass()) {
			return false;
		}
		
		// deep comparison at this point
		// type casting since we know it is guaranteed MyClass
		MyClass obj = (MyClass) c;
		
		return obj.name == this.name && obj.date == this.date;
	}
}
```


# References
https://www.geeksforgeeks.org/java/equals-hashcode-methods-java/