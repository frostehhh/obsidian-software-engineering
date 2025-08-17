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
## How to handle 


# Questions
