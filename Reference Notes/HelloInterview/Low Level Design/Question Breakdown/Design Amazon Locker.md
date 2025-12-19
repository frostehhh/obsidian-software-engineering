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

```java
class Locker {
	- compartments
	  
	+ getAvailableCompartments(size)
	+ depositInCompartment
}

enum CompartmentSize {
}

class Compartment {
	- size
	- item
	- accessToken
	  
	+ inputAccessCode(code)
}

class CompartmentAccessCode {
	- code
	- expiryDate
	
	+ validateCode(code)
}
```

# Implementation

# Extensibility and Maintainability


