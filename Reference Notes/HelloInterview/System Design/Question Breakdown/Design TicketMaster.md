---
tags:
  - guide
  - reference-notes
  - system-design/case-study
draft: false
source_url: https://www.hellointerview.com/learn/system-design/problem-breakdowns/ticketmaster
has-questions: true
---

# Requirements
## Functional
1. Users should be able to view events
2. Users should be able to search for events
3. Users should be able to book tickets to events

## Non-functional
1. The system should prioritize availability for searching & viewing events, but should prioritize consistency for booking events (no double booking)
2. The system should be scalable and able to handle high throughput in the form of popular events (10 million users, one event)
3. The system should have low latency search (< 500ms)
4. The system is read heavy, and thus needs to be able to support high read throughput (100:1)
# Core Entities
- user
- Event
- Booking
- Ticket
- Venue
- Performer
# High-level Architecture
# Deep Dives
# Questions
- What is saga pattern?([ref](https://www.hellointerview.com/learn/system-design/problem-breakdowns/gopuff#comment-clu3appwv00k2mmkqod4w8eav))
- when to add more shards to horizontal partitioning? sharding?
