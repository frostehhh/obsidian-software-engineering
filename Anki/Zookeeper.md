---
tags: 
  - flashcards/system-design
  - backend
  - system-design
  - tool
---

What is Zookeeper and what are its main responsibilities in distributed systems?
?
Zookeeper is a distributed system coordinator that handles:
- Failure detection
- Service discovery
- State management
<!--SR:!2025-06-28,14,290-->
+++

What is a ZNode in Zookeeper and how is it organized?
?
A ZNode is an entity handled by Zookeeper that can represent a server or user. ZNodes are organized like a file system hierarchy, for example:
```
/chat-app
    /servers
        /server1
        /server2
    /config
        /max-users
```
<!--SR:!2025-06-29,15,290-->
+++

What are the three types of ZNodes in Zookeeper?
?
1. Persistent - Exists until manually deleted
2. Ephemeral - Short-lived nodes that exist only during the active session that created them
3. Sequential - Nodes with incrementing IDs
<!--SR:!2025-06-30,16,290-->
+++

How does Zookeeper handle leader election?
?
Zookeeper handles leader election using sequential ZNodes:
- Multiple servers get sequential numbers
- Server with smallest sequence number becomes leader
- Other servers are aware of the leader
- When leader fails, server with next consecutive number takes over
<!--SR:!2025-07-02,7,270-->
+++

What is the difference between read and write operations in Zookeeper?
?
- Reads can be queried from either leader or follower nodes
- Writes must be directed to leader nodes only
<!--SR:!2025-06-28,14,290-->
+++

How does Zookeeper handle service discovery?
?
Service discovery in Zookeeper works through:
1. Reading children of a service path (e.g., /streaming/services/video-transcoder)
2. Caching the list locally
3. Connecting to one instance from the list
4. Watching for changes to stay updated
<!--SR:!2025-06-30,5,250-->
+++

When should you choose Zookeeper over Redis for distributed locks?
?
Choose Zookeeper when you don't need high-performance requirements for high-speed lock changes (less than 100 locks per second). Redis is better for high-frequency lock operations.
<!--SR:!2025-06-30,16,290-->
+++

How does Zookeeper handle session management?
?
Zookeeper manages sessions through:
1. Session creation - when client connects
2. Session heartbeat - periodic client pings
3. Session Recovery - allows reconnection within timeout, even to different server
4. Session expiration - occurs when timeout is reached
<!--SR:!2025-06-30,5,230-->
+++ 