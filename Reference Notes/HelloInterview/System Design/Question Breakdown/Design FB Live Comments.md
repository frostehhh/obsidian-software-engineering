---
tags:
  - guide
  - reference-notes
  - system-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/system-design/problem-breakdowns/fb-live-comments
---

# Requirements
## Functional
**Core Requirements**
1. Viewers can post comments on a Live video feed.
2. Viewers can see new comments being posted while they are watching the live video.
3. Viewers can see comments made before they joined the live feed.

**Below the line (out of scope):**
- Viewers can reply to comments
- Viewers can react to comments

## Non-functional
1. The system should scale to support millions of concurrent videos and thousands of comments per second per live video.
2. Availability over consistency but maintain order of messages
3. Low latency reads and writes of messages < 500ms

# Core Entities
- User
- Comment
- Feed

# API
```
// Retrieve only page of comments on join of live feed
GET /feed/:id/comments - Page<Comment>

// Websockets
syncComment(comment: string)
onmessage(comments)
```

# High-level Architecture
![[Design FB Live Comments 2025-07-06 14.56.43.excalidraw]]

# Deep Dives
## How can we ensure comments are broadcasted to viewers in real-time?
2 choices:
- Websockets
- SSE
### Websockets
- requires handlers to expect the websocket protocol
- High implementation complexity
- May not be reasonable to use since there is a large difference between a user's messages and the total messages of all users
### SSE
- works on top of HTTP
- Reasonable for this case where there is a large difference between the rate of a user sending messages vs total messages being sent

## How will the system scale to support millions of concurrent viewers?
## Pub/Sub
Can be using Kafka or Redis
- Initially, can be using 1 pub/sub instance where all remote messaging services will subscribe to
- Since the 1 pub/sub instance may be a bottleneck, we may need to partition the pub/sub service so that each partition will be for a specific remote messages service
- Lastly, we must consider proper load balancing. For instance, we may use consistent hashing so that messages for a certain videoId will consistently be messaged by a certain remote messaging service
### Zookeeper

# Questions
