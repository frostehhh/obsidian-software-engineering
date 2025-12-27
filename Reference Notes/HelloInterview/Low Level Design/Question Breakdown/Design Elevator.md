---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/low-level-design/problem-breakdowns/elevator
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
## Questions
- Do we need consideration for 
	- emergency button
	- max weight?
	- cancellation of queues
	- emergency comms
	- 
# Entities and Relationships
ElevatorSystem class - public API
Elevator
# Class Design
```java

enum Direction {
	UP,
	DOWN,
	NONE,
}
enum RequestType {
	PICKUP_UP,
	PICKUP_DOWN,
	FLOOR,
}
record ElevatorRequest(RequestType rt, int floor) {}

class ElevatorSystem {
	Elevator[] elevators;
	int floors;
	
	ElevatorSystem()
	
	public void hallCallRequest(Direction d, int floor)
	public void floorRequest(String elevatorId, int floor)
	public void simulateStep() // movement - 1 tick = 1 move if there exists at least one element in the queue
	
	// ...getters
}

class Elevator {
	int floor = 0;
	List<Integer> floorQueue = new ArrayList<>();
	Direction direction = Direction.UP;
	
	Elevator()
	public void appendQueue(int floor)
	public void toggleDirection()
	public void step(Direction dir)
	
	// ...getters
}
```
# Implementation
```java

enum Direction {
	UP,
	DOWN,
	NONE,
}
enum RequestType {
	PICKUP_UP,
	PICKUP_DOWN,
	FLOOR,
}
record ElevatorRequest(RequestType rt, int floor) {}

class ElevatorSystem {
	Elevator[] elevators;
	int floors;
	
	ElevatorSystem()
	
	public void hallCallRequest(Direction d, int floor) {
		/*
			- validate the floor
			- if invalid, end here
			- if valid, proceed
			- selection logic for which elevator to handle this request
			- request creation
			- appending of request to selected elevator
		*/
		if (floor > floors) {
			throw new RuntimeException("Invalid floor");
		}
		RequestType rt = d == Direction.UP ? RequestType.PICKUP_UP : PICKUP_DOWN;
		Request req = new Request(rt, floor);
		
		// select elevator that requires the least steps.
		// for each elevator, calculate distance
	}
	private int calculateStepsFromRequest(Request req, Elevator el) {
		
	}
	public void floorRequest(String elevatorId, int floor)
	public void simulateStep() // movement - 1 tick = 1 move if there exists at least one element in the queue
	
	// ...getters
}

class Elevator {
	int floor = 0;
	List<Integer> floorQueue = new ArrayList<>();
	Direction direction = Direction.UP;
	
	Elevator()
	public void appendQueue(int floor)
	public void toggleDirection()
	public void step(Direction dir)
	
	// ...getters
}
```

# Sample Flow
Flows to consider
- happy path
- idle elevators
- 
```java
ElevatorSystem s = new ElevatorSystem()
s.hallCallRequest(Direction.UP, 3)
	Elevator.appendQueue(3)
Elevator.simulateElevators()
```

# Extensibility and Maintainability