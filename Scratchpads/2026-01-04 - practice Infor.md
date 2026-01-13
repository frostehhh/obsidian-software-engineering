---
date: "2026-01-04T13:57"
---

I have a coffee shop and I need software to manage my employees, customers, and their orders
* I want to keep track of employee IDs and names
* My shop sells coffee and pastries
* Customers can have multiple orders of both coffee and pastries
* I only sell two types of coffee, black and decaf. Black comes in tall and grande, but Decaf is available as tall, grande and venti
* I only sell one type of pastry, donuts.
* I want to have a record of all orders made at my shop
* I want to be able to track the orders that each employee handles
* I have a frequent customer program. Customers under this program automatically gets their drink upsized or if they have the largest drink, they get a free donut.

```java


// entities
customer
employee
order
orderItem
ItemCategory
item


class CoffeeShopController {
	public static handleOrder(Order o) {
		
		Order o = handleFrequentCustomer(o);
		
		return cost;
	}

	public static handleFrequentCustomer (Order o) {
		// query if customer is frequent
		if (o.customer.isFrequentCustomer()) {
			Order updatedOrder = updateOrder(o);
		}
	}
}

class Person {
	String id;
	String name;
}

class Employee extends Person {}

class Customer extends Person {
	private int visitsInPast30Days;
	private static final int frequentCount = 5;
	
	public boolean isFrequentCustomer() {
		return visitsInPast30Days >= frequentCount;
	}
}

class Order {
	String id;
	String employeeId;
	String customerId;
	OrderItem[] items;
	OffsetDateTime created_at; 
}

class OrderItem {
	String id;
	String itemId;
	int quantity;
	String size;
}

enum CoffeeType {
	BLACK,
	DECAF,
}

class CoffeeItem extends OrderItem {
	CoffeeType cType;

	public boolean validateOrder() {
		if (coffeeType == CoffeeType.BLACK && this.size == CoffeeSize.VENTI) {
			throw new RuntimeError("")	
		}
		
		return true;
	}
}

enum CoffeeSize {
	TALL,
	GRANDE,
	VENTI,
}

enum ItemCategory {
	COFFEE,
	PASTRIES,
}

class Item {
	String id;
	String name;
	String description;
	ItemCategory category;
}
```
