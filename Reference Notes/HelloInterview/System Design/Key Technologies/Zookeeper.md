---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/zookeeper
Draft: true
has-questions: true
---

- Distributed System coordinator
- Handles nuances specific to distributed systems
	- Failure detection
	- Service discovery
	- State management

# Basics
## ZNode
- An entity handled by Zookeeper
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
	- 
## Watches
- A mechanism for ZooKeeper to inform servers of changes that those servers are watching

## Ensemble
- Leader-follower pattern

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
# How Zookeeper Works

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
## Durability
- [[Write-Ahead Log|WAL]]
- Snapshots
## Failure Handling


# Questions
- When do you use each type of ZNode?
- In ZooKeeper Atomic Broadcast, why is it that a majority and not all need to confirm the broadcasted changes? is it for speed?