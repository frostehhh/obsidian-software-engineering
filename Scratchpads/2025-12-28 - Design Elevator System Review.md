---
tags:
  - guide
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/elevator
"origin:": "[[Design Elevator]]"
---

# Problem
**🛗 What is an Elevator System?** An elevator system manages multiple elevators serving different floors in a building. When someone requests an elevator, the system decides which one to dispatch. Once inside, passengers select their destination floors. The system needs to move elevators efficiently while handling multiple concurrent requests.

# Requirements
Design an elevator control system for a building. The system should handle multiple elevators, floor requests, and move elevators efficiently to service requests.

1. System manages 3 elevators serving 10 floors (0-9)
2. Users can request an elevator from any floor (hall call). System decides which elevator to dispatch.
3. Once inside, users can select one or more destination floors
4. Simulation runs in discrete time steps (e.g., a `step()` or `tick()` call advances time)
5. Elevator stops come in two types:
    - Hall calls: Request from a floor with direction (UP or DOWN)
    - Destination: Request from inside elevator (no direction specified)
6. System handles multiple concurrent pickup requests across floors
7. Invalid requests should be rejected (return false)
    - Non-existent floor numbers
8. Requests for the current floor are treated as a no-op / already served (doors out of scope)

Out of scope:
- Weight capacity and passenger limits
- Door open/close mechanics
- Emergency stop functionality
- Dynamic floor/elevator configuration
- UI/rendering layer

# Entities and Relationships
- ElevatorSystem or ElevatorController - API for interacting with the elevator system as a whole
- Elevator - individual elevator unit
# Class Design and Implementation
```java
enum Direction {
	UP,
	DOWN,
	IDLE,
}
class ElevatorController {
	private List<Elevator> elevators;
	private int floors = 9;
	
	public ElevatorController(List<Elevator> elevators)
	
	// ...getters
	
	private boolean validateFloorRequest(Direction dir, int floor) {
		// validate if floor and direction is valid
		// 0 to 9 floor numbers
		// 0 down is not allowed
		// 9 up is not allowed
	}
	private void selectBestElevatorForRequest(Direction dir, int floor) {
		// What algorithm can we have here?
		// down to up/up to down
		
		// least busy
		// already in incoming direction
		// least steps/effort
		
		// get requests of each elevator, current floor and direction
		// based on those information, identify which is best to take the
		// request
	}
	// Request from hall call
	public void requestPickup(Direction dir, int floor) {
		validateFloorRequest(dir, floor)
		selectBestElevatorForRequest(dir, floor)
	}
	// Request from within elevator
	public void requestFloor(int floor)
	// simulate elevator functionalities and movement
	public void step()
}

enum class RequestType {
	PICKUP_UP,
	PICKUP_DOWN,
	FLOOR,
}
record FloorRequest(RequestType dir, int floor) {}
class Elevator {
	Direction direction = Direction.IDLE;
	int floor = 0;
	List<FloorRequest> requests = new List<>();
	
	public Elevator(int floor) {}
	
	// Append request to the requests list
	public void addRequest(Direction dir, int floor)
	// move a floor or open door at a floor
	public void step(Direction dir) {
		/*
			If no requests
				Direction.IDLE
			If has requests
				Continue going in current direction if:
				- there are floor only requests that can be approached in the direction
				- there are floor requests that match the current direction of the elevator and the elevator will go to
				Update floor by +1/-1 depending on direction to move towards next request
			If at floor where a request can be fulfilled:
				- clear request from requests list
				- identify if will continue going up or down.
				  Can use hasRequestInDirection
				  
		*/
		// go up
		// go down
		// idle
		// open
	}
	/*
	For example, floor is at 5 and direction is UP, check if we stay idle, go down or continue going up. Continue going up if there is a request at a higher floor
	*/
	public boolean hasRequestsInDirection(Direction dir) {
		/*
			Get current floor and direction
			Check if there are existing requests that match 
		*/
	}
}
/*
*/

/*
	Algorithms for selection of next elevator
	1. FIFO queue
	2. Nearest request
	3. Up to down/down to up - best 
*/
```

**Simulation**
List of requests

Elevator 1

| Current floor | Request Floor | Request Direction |
| ------------- | ------------- | ----------------- |
| 0             | 0             | UP                |
| 0             | 9             | DOWN              |
| 2             | 5             | UP                |
| 3             | 6             | DOWN              |
|               |               |                   |


# Implementation

# Extensibility and Maintainability

