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



# Scaling



hot key issue
key space
# Use Cases
## Cache
- Temporary data store for data previously accessed from a database
- May use LRU especially when memory is maxed out

## Rate limiting
- Can be used for rate limiting APIs
```
task_service_max_limit 5 LT 60 //
```


## Stream - Event Sourcing
Single stream of messages to consume -> multiple workers to process them

## Sorted Sets
popular tweets by likes example
## Geospatial Index
## PubSub



# Questions
key spaces, how do you configure?

# References
https://redis.io/docs/latest/develop/data-types/streams/