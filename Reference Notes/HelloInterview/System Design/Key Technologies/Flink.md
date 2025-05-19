---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/flink
Draft: true
has-questions: false
---

# Concepts
## Source
where stream data comes from
## Streams
flow of data
## Operator
transformations to be done on streams
## Sink
Where to output transformed data
## Watermark
- a time signpost signifying data generated before time X(example Watermark for entries generated before 5pm, which also includes late sent entries)
- Configurations
	- Bounded out-of-orderness - specified time limit how long Flink will wait for late entries 
	- No watermark - Don't access any late entries
## Windows
- Grouping of data
### Types
1. Tumbling - non-overlapping
2. Sliding - overlapping
3. Session - activity based
4. Global - custom window logic

# Usage
## Defining a Job
Define(can be in code) the source, sink, streams and operators
## Submitting a Job
Run `execute` command after defining

# How Flink Works
# Flink in System Design