# Clones
Public servers of a scalable web service are hidden behind a load balancer. Sessions should not be stored in these servers but in an external store like a persistent cache or database.

# Database
Database implementation plays a huge part in scaling. For example, SQL database with many joins is much less performant compared to minimal number of joins/using NoSQL. 

# Cache
Cache is a key-value store that stores data between application and primary data storage. 

## Main patterns for caching
1. Cached Database Queries
2. Cached objects

# Asynchronism
Async processing avoids idle waiting times.
1. Perform resource-intensive task prior to retrieval of relevant data
2. Wait for prompt to perform resource-intensive task, and on prompt, allow user to perform other tasks while waiting for the task to accomplish

# References
https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#step-2-review-the-scalability-article