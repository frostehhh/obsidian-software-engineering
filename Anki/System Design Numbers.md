---
tags:
  - flashcards/system-design
  - system-design
  - performance
  - scalability
Draft: true
---

What is the typical latency for caching operations?::~1 millisecond
<!--SR:!2025-07-12,60,310-->

How many operations per second can a cache typically handle?::100k+ operations/second
<!--SR:!2025-07-12,60,310-->

What is the typical memory capacity limit for caching?::Up to 1TB (memory-bound)
<!--SR:!2025-07-12,60,310-->

At what hit rate should you consider scaling your cache?::When hit rate drops below 80%
<!--SR:!2025-07-12,60,310-->

What are the key scale triggers for caching systems?::Hit rate < 80%, Latency > 1ms, Memory usage > 80%, Cache churn/thrashing
<!--SR:!2025-07-12,60,310-->

How many transactions per second can databases typically handle?::Up to 50k transactions/second
<!--SR:!2025-07-12,60,310-->

What is the expected read latency for cached database queries?::Sub-5ms read latency
<!--SR:!2025-07-12,60,310-->

What is the typical storage capacity for databases?::64 TiB+ storage capacity
<!--SR:!2025-07-12,60,310-->

At what write throughput should you consider database scaling?::When write throughput exceeds 10k TPS
<!--SR:!2025-07-12,60,310-->

What are the main database scale triggers?::Write throughput > 10k TPS, Read latency > 5ms uncached, Geographic distribution needs
<!--SR:!2025-07-12,60,310-->

How many concurrent connections can app servers typically handle?::100k+ concurrent connections
<!--SR:!2025-07-12,60,310-->

What is the typical CPU configuration for app servers?::8-64 cores @ 2-4 GHz
<!--SR:!2025-07-12,60,310-->

What is the standard RAM range for app servers?::64-512GB RAM standard, up to 2TB
<!--SR:!2025-07-12,60,310-->

At what CPU utilization should you consider scaling app servers?::When CPU > 70% utilization
<!--SR:!2025-07-12,60,310-->

What are the key app server scale triggers?::CPU > 70% utilization, Response latency > SLA, Connections near 100k/instance, Memory > 80%
<!--SR:!2025-07-12,60,310-->

How many messages per second can message queues handle per broker?::Up to 1 million msgs/sec per broker
<!--SR:!2025-07-12,60,310-->

What is the typical end-to-end latency for message queues?::Sub-5ms end-to-end latency
<!--SR:!2025-07-12,60,310-->

What is the storage capacity for message queues?::Up to 50TB storage
<!--SR:!2025-07-12,60,310-->

At what throughput should you consider scaling message queues?::When throughput approaches 800k msgs/sec
<!--SR:!2025-07-12,60,310-->

What are the main message queue scale triggers?::Throughput near 800k msgs/sec, Partition count ~200k per cluster, Growing consumer lag
<!--SR:!2025-07-12,60,310-->

What are the top 3 mistakes to avoid in system design regarding performance?::1. Premature Sharding, 2. Overestimating latency, 3. Over-engineering given high write throughput
<!--SR:!2025-07-12,60,310-->

What does "overestimating latency" mean in system design?::Estimating latency in a scenario as slower than it actually is
<!--SR:!2025-07-12,60,310--> 