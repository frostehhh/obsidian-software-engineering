---
tags:
  - notes
  - backend
  - database
  - redis
  - tool
Draft: false
"related-reference-note:":
  - "[[Reference Notes/HelloInterview/System Design/Key Technologies/Redis|Redis]]"
has-questions: false
---

Redis is a key-value store that supports various types of value types
# Basics
- data-structure key-value store -> key-value pairs with values of various data structures
- In-memory data -> lack of durability
## Scaling
- Scalable horizontally with replicas or clusters
- Structuring keys is fundamental to scaling Redis
# Value types supported
- Generic
- List
- Set
- Sorted Set
- JSON
- Hashes
- Streams
- and more

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
- Single [[Stream]] of messages to consume -> multiple workers to process them
## Sorted Sets
popular tweets by likes example
- Can be used for leaderboards
## Geospatial Index
Stores location/coordinations
## PubSub
[`SUBSCRIBE`](https://redis.io/docs/latest/commands/subscribe/), [`UNSUBSCRIBE`](https://redis.io/docs/latest/commands/unsubscribe/) and [`PUBLISH`](https://redis.io/docs/latest/commands/publish/) implement the [Publish/Subscribe messaging paradigm](http://en.wikipedia.org/wiki/Publish/subscribe) where (citing Wikipedia) senders (publishers) are not programmed to send their messages to specific receivers (subscribers).[^1]

# Issues to take note of
## Hot Key
- Occurs in a scaled Redis infrastructure with clusters(shards)
- Load is focused on a shard - imbalance in load distribution

# References
https://redis.io/docs/latest/develop/data-types/streams/

[^1]: https://redis.io/docs/latest/develop/interact/pubsub/
