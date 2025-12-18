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
Payment method example
Abstraction via `PaymentMethod.pay()`
```java
interface PaymentMethod {
	public boolean pay();
}

class CreditCardPayment implements PaymentMethod {
	public boolean pay() {...}
}

class CashPayment implements PaymentMethod {
	public boolean pay() {...}
}

class OrderService {
	private PaymentMethod
	public boolean processOrder(PaymentMethod paymentMethod, ...) {
		paymentMethod.pay(...);
	}
}
```

# Polymorphism
- Alternative for switch statements in OOP
- Given a parent class or interface, the implementation changes based on the subclass
## Example
Refer to the [[#Example|Abstraction Example]]. The implementation for `pay` in `CreditCardPayment` and `CashPayment` are different
# Inheritance
- Base class methods and fields that are inherited by a subclass
- Tightly couples code
- Updates to parent class directly affects subclasses
- As a better alternative to prevent tight coupling, before using inheritance, use a combination of composition + interfaces
- Better to use inheritance for stable base class implementations
## Example
```java
abstract class BankAccount {
  protected double balance;

  public void deposit(double amount) {
    balance += amount;
  }

  public boolean withdraw(double amount) {
    if (balance < amount) return false;
    balance -= amount;
    return true;
  }

  public double getBalance() {
    return balance;
  }
}

class SavingsAccount extends BankAccount {
  private double interestRate;
}

class CheckingAccount extends BankAccount {
  private int overdraftLimit;
}


```