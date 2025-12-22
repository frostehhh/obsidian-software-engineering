---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/amazon-locker
"origin:": "[[Design Amazon Locker]]"
---

# Problem
Design a locker system like Amazon Locker where delivery drivers can deposit packages and customers can pick them up using a code.

# Requirements
- **Delivery Driver** deposits **packages** to **Locker Unit**
- **Customer** can pickup via code their **package** from a **Locker Unit**
- **Compartments** have different sizes
- Codes can expire -> max 7 days
- 1 **package**: 1 **Locker Unit**
- Customers can have multiple packages

## Out of Scope
Logistics of Delivery driver
Delivery of package code to customer
# Entities and Relationships
Locker -> public API
Compartment ->
AccessCode

1 Locker : Many Compartments
1 Compartment : 1 AccessCode

# Class Design

```java
class Locker {
	List<Compartment> compartments;
	Map<String, AccessCode> mapIdToCode;
	
	public { compartmentId, tokenCode } deposit(size)
	public boolean pickup(compartmentId, code)
	
	// ...getters
}

enum CompartmentSize {
	SMALL,
	MEDIUM,
	LARGE,
}

class Compartment {
	String id;
	CompartmentSize size;
	
	Compartment(id, size)
	getCompartment(id)
	
	// ...getters
}

class AccessCode {
	String code;
	String compartmentId;
	Instant expiryDatetime;
	
	// getters
}
```

# Implementation

```java
class Locker {
	List<Compartment> compartments;
	Map<String, AccessCode> mapIdToCode;
	
	public { compartmentId, tokenCode } deposit(size) {
	
	}
	// on input of code, if it matches, it will open a compartment door
	public boolean pickup(code) {
		/*
			check if code has value
			check if code exists
			check if code matches. If yes, if compartment is not expired
		*/
		
		if (!code) {
			
		}
		
	}
	
	// ...getters
}

enum CompartmentSize {
	SMALL,
	MEDIUM,
	LARGE,
}

class Compartment {
	String id;
	CompartmentSize size;
	
	Compartment(id, size)
	getCompartment(id)
	
	// ...getters
}

class AccessCode {
	String code;
	String compartmentId;
	Instant expiryDatetime;
	
	// getters
}
```
# Extensibility and Maintainability