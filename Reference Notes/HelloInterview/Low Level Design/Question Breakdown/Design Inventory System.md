---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/inventory-management
---

# Problem

"Design an inventory management system that tracks products across multiple warehouses. The system needs to handle adding and removing inventory, transferring stock between locations, and alerting when inventory runs low."

## Questions
- Are there different types of products? What information must we need to store per product?
- How many warehouses are there?
- When do we want to consider that a stock is low? Is there configuration for that ideally?
- Do we include implementation details for alerting? or can we abstract the details of that?
- Do we need to consider logistics?
# Requirements
1. Track inventory for products across multiple warehouses
2. Add stock to a specific warehouse (receiving shipments)
3. Remove stock from a specific warehouse (fulfilling orders)
4. Check availability: given a product and quantity, return which warehouses can fulfill it
5. Transfer stock between warehouses
6. Low-stock alerts
7. Reject operations that would result in negative inventory
8. System must be thread-safe to handle concurrent operations

Out of Scope:
- Product catalog management (products exist externally)
- Order processing / payment / serviceability
- Persistence

# Entities and Relationships
- Warehouse
- product

1 warehouse : many products

|Entity|Responsibility|
|---|---|
|**InventoryManager**|The orchestrator. Owns all warehouses and coordinates operations across them. When you want to transfer stock, check availability across multiple locations, or configure alerts, you go through this class. It's the only public API for the system.|
|**Warehouse**|Represents a single storage location. Holds a map of productId → quantity. Enforces the "no negative stock" invariant. Owns its alert configurations and fires alerts when stock changes trigger thresholds. Doesn't know about other warehouses.|
|**AlertConfig**|A value object grouping the threshold and the listener to notify when stock drops below that threshold.|
|**AlertListener**|An interface defining the callback contract. Implementations receive warehouse ID, product ID, and current quantity when stock drops below a threshold. This decouples "stock is low" from "what to do about it."|

# Class Design
```java
class InventoryManager {
	public InventoryManager() {}

	public addStock(warehouseId, productId, quantity)
	public removeStock(warehouseId, productId, quantiy)
	public transferStock(warehouseA, warehouseB, productId, quantity)
	public List<Warehouse> getWarehousesWithAvailability(productId, quantity) returns list of warehouse IDs
	public void setLowStockAlert(warehouseId, productId, threshold, listener)
}

class Warehouse {
	String warehouseId;
	Map<String, Integer> stocks;
	Map<String, AlertConfig> alertConfigs;
	
	public Warehouse(String warehouseId, Map<String, Integer> stocks) {
	}
	public void setLowStockAlert(productId, threshold, listener)
}

class AlertConfig {
	int threshhold;
	AlertListener alertListener;
}

interface AlertListener {
	// pass output quantity
	public void listen(warehouseId, productId, quantity)
}

```

# Implementation

```java
class InventoryManager {
	private Map<String, Warehouse> warehouses = new HashMap<>();
	
	public InventoryManager(List<Warehouse> warehouses) {
		this.warehouses = // convert list of warehouses to map;
	}

	public addStock(warehouseId, productId, quantity) {
		Warehouse warehouse = warehouses.get(warehouseId);
		warehouse.addStock(productId, quantity);
	}
	public removeStock(warehouseId, productId, quantity) {
		Warehouse warehouse = warehouses.get(warehouseId);
		warehouse.removeStock(productId, quantity);
	}
	public transferStock(warehouseA, warehouseB, productId, quantity) {
		Warehouse whA = warehouses.get(warehouseA);
		Warehouse whB = warehouses.get(warehouseB);
		
		if (warehouseA.getStocks(productId) >= quantity) {
			whB.addStock(productId, quantity);
			whA.removeStock(productId, quantity);
		}
	}
	public List<Warehouse> getWarehousesWithAvailability(productId, quantity) {
		// use warehouse.getStocks(productId) and compare with quantity. Return all warehouses that have enough stocks
	}
	public void setLowStockAlert(warehouseId, productId, threshold, listener)
}

class Warehouse {
	String warehouseId;
	Map<String, Integer> stocks;
	Map<String, AlertConfig> alertConfigs;
	
	public Warehouse(String warehouseId, Map<String, Integer> stocks) {
	}
	
	public void addStock(String productId, int quantity) {
		// validate if productId and quantity have a value
		// validate if productId exists
		
		stocks.put(productId, stocks.get(productId) + quantity)
	}
	
	public int getStocks(String productId) {
		return stocks.get(productId);
	}
	
	public void removeStock(String productId, int quantity) {
		// validate if productId and quantity have a value
		// validate if productId exists
		// validate if requests to remove X number of quantity is valid
		
		stocks.put(productId, stocks.get(productId) - quantity)
		
		List<AlertConfig> alertConfigs = // use checkIfLowStockAlert to return list
		for (AlertConfig ac : alertConfigs) {
			setLowStockAlert(productId, threshhold, listener);
		}
	}
	public void setLowStockAlert(productId, threshold, listener) {
			
	}
	
	private List<AlertConfigs> checkIfLowStockAlert(productId) {
	
	}
}

class AlertConfig {
	int threshhold;
	AlertListener alertListener;
}

interface AlertListener {
	// pass output quantity
	public void onLowStock(warehouseId, productId, quantity)
}

class MailAlertListener implements AlertListener {
	public void onLowStock(warehouseId, productId, quantity) {
		// send email alert
	}
}

class SMSAlertListener implements AlertListener {
	public void onLowStock(warehouseId, productId, quantity) {
		// send sms alerts
	}
}

```

# Extensibility and Maintainability

