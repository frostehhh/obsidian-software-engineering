---
tags:
  - system-design
"Parent:":
  - "[[Reference Notes/HelloInterview/System Design/System Design|System Design]]"
---

# Simple DB-backed CRUD service with caching
Typically contains the following components:
- Client
- API Gateway - directs requests to corresponding service
- Load balancer - reverse proxy in front of a service
- Service
- Service-level cache
- Database

# Async job worker pool
Involves a queue where multiple workers can consume and process messages from the queue. They have the same input source and the same output source

# Two stage architecture
An architecture where for a process that may take time, there can be a "fast" stage and a "slow stage". The fast stage uses a cheaper and less accurate algorithm for more immediate results. The slow stage uses a more complex algorithm for slower to compile but better results.

# Event-Driven Architecture
Involves the following:
- Event producers
- Event routers/brokers
- Event consumers

Common in microservice architectures.
May be tricky to debug when there failure occurs

# Durable Job Processing
- Relevant for long-running jobs that may take hours, days or even weeks
- Ability for a job to be continued despite pausing or failure
- Distributed job workers
# Proximity-Based Services
- Geospatial querying
- Relevant for services like Uber, Grab
- Geospatial index may be good particularly if there is at least hundred thousands of data