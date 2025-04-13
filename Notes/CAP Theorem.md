---
tags:
  - database
  - notes
Draft: false
---

# Consistency
- Every read receives the most recent data
- There can be multiple nodes but strong consistency
# Availability
- Every request must result to a response
- Request to a dead node must fallback to a "live" node
# Partition Tolerance
- Ability for nodes to continue communicating despite failed communications between each other

# References
https://en.wikipedia.org/wiki/CAP_theorem
https://www.ibm.com/think/topics/cap-theorem