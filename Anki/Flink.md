---
tags: 
  - flashcards/system-design
  - backend
  - system-design
  - tool
---

What are the main concepts in Apache Flink's stream processing architecture?
?
The main concepts in Flink are:
1. Source - where stream data comes from
2. Streams - flow of data
3. Operator - transformations done on streams
4. Sink - where transformed data is output
<!--SR:!2025-07-31,25,290-->
+++

What is a Watermark in Flink and what are its configuration options?
?
A Watermark is a time signpost signifying data generated before time X. It has two configuration options:
1. Bounded out-of-orderness - specified time limit for how long Flink will wait for late entries
2. No watermark - Don't access any late entries
<!--SR:!2025-08-31,61,310-->
+++

What are the different types of Windows in Flink?
?
Flink supports four types of windows for data grouping:
1. Tumbling - non-overlapping windows
2. Sliding - overlapping windows
3. Session - activity based windows
4. Global - custom window logic
<!--SR:!2025-11-08,106,290-->
+++

What are the two main types of processes in Flink's cluster architecture and their roles?
?
1. Job Manager:
   - Administrates processes
   - Handles checkpoints
   - Handles failures
   - Allocates tasks
   - Can have replicas for failover

2. Task Manager:
   - Has Task slots
   - Reserves memory for computation
   - Task slots can share resources when working on same job
<!--SR:!2025-09-21,64,290-->
+++

What are the supported State Management options in Flink?
?
Flink supports three state management options:
1. JVM heap - in memory
2. Filesystem
3. RocksDB - key-value store that utilizes disk space
<!--SR:!2025-08-06,15,230-->
+++

What is the process of handling failures in Flink?
?
Flink handles failures through these steps:
1. Failure detection
2. Job Pause
3. Go back to recent checkpoint
4. Redistribute tasks from failed task managers
5. Task managers reset to previous checkpoint
6. Operators reset to previous checkpoint
7. Resume Job processing
<!--SR:!2025-07-27,20,250-->
+++

When should you use Flink in a system design?
?
Use Flink:
- When you need real-time processing of stream data
- Usually with Kafka as the source
- When you need features like:
  - Window grouping of data
  - Watermark concept
  - State management
  - Exactly-once processing
  - Resource isolation
<!--SR:!2025-08-11,41,290-->
+++ 