---
tags:
  - backend
  - notes
  - software-architecture
  - pattern
aliases:
  - Event Sourcing
Draft: false
"similar:":
  - "[[Message Queue]]"
"related-reference-note:":
  - "[[Key Technologies]]"
---

- A sequence of data, typically events, where each entry can be read by multiple consumers
- Real-time event capture
- Like an append-only log file
	- Data can be reprocessed
- Can have multiple producers

# Use Cases
- Need to handle large number of requests to avoid overload
# References
https://kafka.apache.org/documentation/#gettingStarted