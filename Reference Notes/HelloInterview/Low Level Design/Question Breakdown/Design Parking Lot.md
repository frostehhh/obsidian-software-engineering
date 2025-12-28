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
	private Map<ParkingSlot, Ticket> slotsToTicketMapping;
	
	public ParkingController() {
		...
	}
	
	public Ticket handleVehicleEntry(VehicleType vType, Instant timestamp) {
		/*
			validate vType and timestamp
			Check if there are available slots for the given vehicleType
			If slot exists,
		      - create Ticket
			  - update parkingSlots, availableParkingSlots, slotsToTicketMapping
			else, 
				reject and throw error
		*/
	}
	public boolean handleVehicleExit(Ticket ticket) {
		/*
			compute actual price based on ticket data
			hours to compute is rounded to the nearest hour
			
			Update parkingSlots and availableParkingSlots
		*/
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
	
	public void occupy
	
	// ...getters
}

class Ticket {
	string id;
	VehicleType vType;
	Instant entryTime;
}
```

# Implementation

# Extensibility and Maintainability

