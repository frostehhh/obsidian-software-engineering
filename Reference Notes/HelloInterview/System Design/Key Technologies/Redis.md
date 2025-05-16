---
tags:
  - reference-notes
  - backend
  - redis
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/redis
has-questions: false
Draft: false
---

Redis is a single-threaded in-memory data-structure store, which is often used as a cache.
# Basics
- data-structure key-value store -> key-value pairs with values of various data structures
- In-memory data -> lack of durability
## Scaling
- Scalable horizontally with replicas or clusters
- Structuring keys is fundamental to scaling Redis
# Use Cases
## Cache
- Temporary data store for data previously accessed from a database
- Can include TTL value as expiry value
- May use LRU especially when memory is maxed out
- "hot-key" problem

## Distributed Lock
- Ensure only 1 entity can access a record or set of records simultaneously
- Not fully consistent
- Better to rely on core database if it can provide better consistency
### Leaderboards
- Use sorted sets
## Rate limiting
- Can be used for rate limiting APIs
```
INCR task_service_rate_limit # 5 
EXPIRE task_service_rate_limitLT 60 
```

## Stream - Event Sourcing
Single stream of messages to consume -> multiple workers to process them
## Sorted Sets
popular tweets by likes example
- Can be used for leaderboards
## Geospatial Index
Stores location/coordinations
## PubSub

# Issues to take note of
## Hot Key
- Occurs in a scaled Redis infrastructure with clusters(shards)
- Load is focused on a shard - imbalance in load distribution
- To resolve, split the key in to multiple different keys to spread across different shards[^1]
	- Monitoring via Prometheus/Grafana to determine shard CPU load
	- Checking via Redis for hot keys
	- 

# References
https://redis.io/docs/latest/develop/data-types/streams/

[^1]: https://igorjovanovic.com/hotkeys-and-bigkeys-issues-in-redis/
