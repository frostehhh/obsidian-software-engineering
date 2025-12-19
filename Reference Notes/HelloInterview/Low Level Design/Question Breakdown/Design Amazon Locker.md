---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/amazon-locker
---

# Problem
Design a locker system like Amazon Locker where delivery drivers can deposit packages and customers can pick them up using a code.

# Requirements
- **Delivery Driver** deposits **packages** to **Locker Unit**
- **Customer** can pickup via code their **package** from a **Locker Unit**
- **Locker Units** have different sizes
- Codes can expire -> max 7 days
- 1 **package**: 1 **Locker Unit**
- Customers can have multiple packages

## Out of Scope
Logistics of Delivery driver
Delivery of package code to customer
# Entities and Relationships
Locker -> public API
Compartment ->
AccessToken

1 Locker : Many Compartments
1 Compartment : 1 AccessToken

# Class Design
## Solution 1
Access code state logic is declared across all entities
```java
class Locker {
	- compartments
	- filledCompartments -> subset of compartments
	  
	+ Locker(compartments)
	+ getFilledCompartments()
	+ unlockCompartment(compartmentId, code)
}

enum CompartmentSize {
	SMALL,
	MEDIUM,
	LARGE,
}

class Compartment {
	- id
	- size
	- AccessCode accessCode
	  
	+ Compartment(size)
	+ getId()
	+ getSize()
	+ validateAccessCode(code)
}

class AccessCode {
	- code
	- expiryDate
	- compartmentId
	  
    + AccessCode(code, expiryDate, compartmentId)
	+ validateAccessCode(compartmentId, code)
}
```

## Solution 2
State logic for access code is located only `Locker` class
This keeps the state handling in one place. Generally more maintainable
```java
class Locker {
	- compartments
	- mappingCompartmentToCode: Map<Compartment, AccessCode>
	- availableCompartments -> subset of compartments
	  
	+ getAvailableCompartments()
	+ unlockCompartment(compartmentId, code)
}

enum CompartmentSize {
	SMALL,
	MEDIUM,
	LARGE,
}

class Compartment {
	- id
	- size

	+ getId()
	+ getSize()
}

class AccessCode {
	- code
	- expiryDate
	- compartmentId
	  
	+ AccessCode(code, expiryDate, compartmentId)
	+ ...getters  
	
}
```
# Implementation
```java
class Locker {
	- compartments
	- mappingCompartmentToCode: Map<Compartment, AccessCode>
	- availableCompartments -> subset of compartments
	  
	+ getAvailableCompartments() {
	  
	  }
	+ unlockCompartment(compartmentId, code)
}

enum CompartmentSize {
	SMALL,
	MEDIUM,
	LARGE,
}

class Compartment {
	- id
	- size

	+ getId()
	+ getSize()
}

class AccessCode {
	- code
	- expiryDate
	- compartmentId
	  
	+ AccessCode(code, expiryDate, compartmentId)
	+ ...getters  
	
}
```

# Extensibility and Maintainability


