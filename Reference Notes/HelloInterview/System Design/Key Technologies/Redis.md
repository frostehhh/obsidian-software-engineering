---
tags:
  - reference-notes
  - backend
  - redis
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/redis
has-questions: true
Draft: true
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
## Leaderboards
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
## Geospatial Index
## PubSub

# Issues to take note of

# Questions
key spaces, how do you configure?

# References
https://redis.io/docs/latest/develop/data-types/streams/