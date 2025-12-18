---
tags:
  - reference-notes
  - low-level-design
  - programming-languages/object-oriented-programming
source_url: https://www.hellointerview.com/learn/low-level-design/in-a-hurry/oop-concepts
---

- Encapsulation
- Abstraction
- Polymorphism
- Inheritance

# Encapsulation
- Control exposed behaviors and state
	- Make fields private
	- Expose methods on how to manipulate and view state to clarify usage
- Good for coupling related logic
## Example
**Bad example**
```java
class Parking{
	public List<ParkingSpot> spots;
}
class ParkingSpot {...}
```
Here, users of the Parking object can freely modify the spots directly

**Good example**
```java
class Parking {
	private List<ParkingSpot> spots;
	
	public void parkVehicle(ParkingSpot p) {...}
	public List<ParkingSpot> getAvailableSpots() {...}
}
```
This restricts the possible behaviors when using the object. Note that the `spots` field is private and methods are added to indicate usage behavior.

# Abstraction
- Hide away implementation details behind an object to hide complexity
- Eases understanding of code
## Example

# Polymorphism
- Alternative for switch statements in OOP
## Example

# Inheritance
- Tightly couples code
- Updates to parent class directly affects subclasses
- As a better alternative to prevent tight coupling, use a combination of composition + inheritance
- Better to use inheritance for stable base class implementations
## Example
