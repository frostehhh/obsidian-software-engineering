---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/cassandra
Draft: false
has-questions: true
---

An open-source distributed NoSQL Database

![[Notes/Apache/Cassandra#Data Model|Cassandra]]

![[Notes/Apache/Cassandra#Key Concepts|Cassandra]]
# How to use Cassandra
## Discord Message Channels
### Initial schema
Contains channel_id and message_id as primary keys
### Issue
Some channels have very high load of messages resulting to hot partitions and degraded performance for those partitions
### Developed schema
Add `bucket: int`, which represents 10 days of data, to primary key
### Result
Channel messages are spread across different partitions to avoid hot partition. Performance fixed

## TicketMaster
### Issue
Some events have very high traffic. Hot partitions
### Initial Schema
Primary key -> `event_id`, `seat_id`

### Developed Schema
Add `section_id` to primary key
### Result
All event data are spread across different partitions

![[Notes/Apache/Cassandra#Advanced Features|Cassandra]]
# Cassandra in System Design
- fast read and write
- Highly scalable
- No need for relational data, complex joins or queries
- availability over consistency
# Questions
- is it schemaless. no
- how do you define a cassandra schema
- 