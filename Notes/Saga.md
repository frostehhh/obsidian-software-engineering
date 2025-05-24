---
tags: 
- notes
- pattern
- microservices
---

The saga pattern coordinates services in a distribute system. Typically uses [[Notes/Publish Subscribe|Pub Sub]] pattern for interaction between services

# Types
## Orchestrating
 - Multiple services interact with each other to coordinate a distributed transaction
 - There is no single coordinating entity the handles the entire transaction
## Coordinating
- Multiple services interact with a coordinating service that handles the entire transaction
