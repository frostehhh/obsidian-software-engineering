---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/zookeeper
Draft: false
has-questions: false
---

- Distributed System coordinator
- Handles nuances specific to distributed systems
	- Failure detection
	- Service discovery
	- State management

# Basics
## ZNode
- An entity handled by Zookeeper
	- Can be a server, a representation of a user
- Types
	- Persistent
	- Ephemeral
	- Sequential
- Organized like a file system
	```
	/chat-app
		/servers
			/server1
			/server2
		/config
			/max-users
	```
## Server Ensemble
- ZNode Coordinator
- Leader-follower pattern
## Watches
- A mechanism for ZooKeeper to inform servers of changes that those servers are watching

# Key Capabilities
## Leader Election
- We can use sequential [[#ZNode]] for simple management of leader election.
- Multiple servers can have a sequential number. The server with the smallest sequence number is the leader
	- Other servers are aware of this
- Failover is straightforward - when the leader server fails, the server with the next consecutive sequence number will take over as leader
## Service Discovery
- Easy service discovery via reading ZooKeeper State
- Example flow
	1. Read /streaming/services/video-transcoder children. Cache locally
	2. Connect to one instance from the list
	3. Watch changes to this to be informed of updates
## Configuration Management
- Configuration can be stored in ZNodes
## Distributed Locks
- handle distributed locks via [[#ZNode]]
- [[Notes/Redis|Redis]] also supports distributed locks. Pick ZooKeeper for when you don't need high performance requirements for high-speed lock changes(100 locks per second)
# Zookeeper Internals

## ZooKeeper Atomic Broadcast
- Communication between zookeeper servers
- When a leader dies, new leader is selected via the following factors:
	- Latest transaction by datetime
	- Highest server ID
## Read and Write Operations
- Reads can be queried via leader or follower
- Writes should be directed to leaders
## Strong Consistency
- atomic
- durability
## Session and Client Connection Management
- Session creation - client connects to ZooKeeper
- Session heartbeat - client sends a heartbeat every X time interval to notify that it is still connected. 
- Session Recovery - client loses connection -> can reconnect within session timeout even to another server  
- Session expiration - expires due to reaching timeout
## Durability
- [[Write-Ahead Log|WAL]]
- [[Snapshots]]
## Failure Handling
- When leader fails scenario, see [[#ZooKeeper Atomic Broadcast]]
- Client failures and session management 

# References
https://zookeeper.apache.org/doc/current/zookeeperProgrammers.html#:~:text=Every%20node%20in%20a%20ZooKeeper,cache%20and%20to%20coordinate%20updates.