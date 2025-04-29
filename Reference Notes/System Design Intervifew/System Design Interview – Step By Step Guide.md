---
tags:
  - reference-notes
source_url: https://youtu.be/bUHFg8CZFws
Channel:
  - System Design Interview
Source:
  - Youtube
Draft: true
media: https://www.youtube.com/watch?v=bUHFg8CZFws
---

Topics mentioned in the video:

- Stages of a typical system design interview: functional requirements (API), non-functional requirements, high-level design, detailed design, bottlenecks and tradeoffs.
- Why requirements clarification is so important.
- What questions to ask the interviewer.
- How to design API.
- Non-functional requirements to consider: scalability, performance, availability, consistency, cost.
- How to define a data model.
- How to scale a SQL database.
- Apache Cassandra high-level architecture.
- Data processing concepts: checkpointing, partitioning, in-memory aggregation, deduplication cache, dead-letter queue, embedded database, state management.
- Data ingestion pipeline concepts: blocking vs non-blocking I/O, buffering and batching, timeouts, retries, exponential backoff and jitter, circuit breaker pattern, software vs hardware load balancing, load balancing algorithms, DNS, health checking and high availability of load balancers, partition strategy, hot partitions, client-side and server-side service discovery, single leader replication and leaderless replication, textual vs binary data formats.
- Data retrieval pipeline concepts: time-series data, data rollup, hot storage, cold storage.
- Types of performance testing: load testing, stress testing, soak testing.
- Health monitoring.
- Audit systems.

# Requirements Clarification
- who will use
- scaling - considering input
- performance - expected output(speed)
- cost vs maintenance

1. functional requirements - System behavior, APIs, operations to support
2. non-functional requirements - system qualities - fast, fault-tolerant

hla

data model



14:49 end

availability vs consistency
24:30 eventual consistency
Cassandra tunable consistency

https://youtu.be/bUHFg8CZFws?t=1499
25:00 how we store
sql
- normalized
- think of entity = table
nosql
- think of queries per presentation of data
- denormalized is okay

cassandra - masterless replication

each nosql database has diff architecture, pros and cons'

29:00 - data processing service

31:22 - data aggregation basics

34:35 - processing service detailed

38:00 - processing service detailed - database writer
41:10 - data ingestion process

blocking vs non-blocking i/o. rate limiting system is good for limiting connections(?)
45:01 - buffering and batching