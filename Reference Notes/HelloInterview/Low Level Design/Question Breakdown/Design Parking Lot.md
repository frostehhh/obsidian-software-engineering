---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/parking-lot
---

# Problem
Design a parking lot system where different types of vehicles can park, and the system manages spot assignment and calculates fees upon exit.
# Requirements
1. Vehicles enter the parking lot and are assigned a designated parking spot. This is unique per ticket ID.
2. Flat hourly rates for all vehicles regardless of type. Simple pricing
3. Reject if no more slots for given vehicle type
4. Supported vehicle types: motorcycle, regular, large
5. Pricing is rounded to the nearest hour

# Entities and Relationships
Vehicle - 
Ticket - record
ParkingController - class
ParkingSlot - class

# Class Design and Implementation

```java

class ParkingController {
	private float HOURLY_RATE = 5.0;
	private List<ParkingSlot> parkingSlots;
	private List<ParkingSlot> availableParkingSlots;
	
	public ParkingController() {
		...
	}
	
	public Ticket handleVehicleEntry(VehicleType vType, Instant timestamp)
	public boolean handleVehicleExit() {
		
	}
	
	// ...getters
}

enum VehicleType {
	MOTORCYCLE,
	REGULAR,
	LARGE,
}
class ParkingSlot {
	string id;
	VehicleType vType;
	boolean occupied;
}

class Ticket {
	string id;
	string parkingSlotId;
	VehicleType vType;
	Instant entryTime;
}
```

# Implementation

# Extensibility and Maintainability

