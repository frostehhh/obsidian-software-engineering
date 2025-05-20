---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/flink
Draft: false
has-questions: false
---

Distributed stream data processing 
# Concepts
## Source
where stream data comes from
## Streams
flow of data
## Operator
transformations to be done on streams
## Sink
Where to output transformed data
## Watermark
- a time signpost signifying data generated before time X(example Watermark for entries generated before 5pm, which also includes late sent entries)
- Configurations
	- Bounded out-of-orderness - specified time limit how long Flink will wait for late entries 
	- No watermark - Don't access any late entries
## Windows
- Grouping of data
### Types
1. Tumbling - non-overlapping
2. Sliding - overlapping
3. Session - activity based
4. Global - custom window logic

# Usage
## Defining a Job
Define(can be in code) the source, sink, streams and operators
## Submitting a Job
Run `execute` command after defining

# How Flink Works
## Cluster Architecture
### Types of Processes
1. Job Manager
2. Task Manager
#### Job Manager
- administrates processes
- Can have replicas that can takeover in case of failure
- handles checkpoints
- handle failures
- allocates tasks to task managers
#### Task Manager
- Has Task slots
- Each task slot reserves memory for computation
- Task slots can share resources with each other especially when working on the same job
## Failure Handling
### State Management
- Recently processed data is stored as state
- distributed snapshot every X interval
#### Supported State Management Options
1. JVM heap - in memory
2. Filesystem
3. RocksDB - key-value store that utilizes disk space(not just RAM)
### Handling Failures
1. Failure detection
2. Job Pause
3. Go back to recent checkpoint
4. Redistribute tasks from failed task managers
5. Task managers reset to previous checkpoint
6. Operators reset to previous checkpoint
7. Resume Job processing
# Flink in System Design
- When you need real-time processing of stream
	- Otherwise, keep [[Kafka]]
- Usually, [[Kafka]] will be the [[#Source]]

# Useful Concepts in Flink design
- Window grouping of data
- Watermark concept
- state management patterns
- exactly-once processing
- resource isolation