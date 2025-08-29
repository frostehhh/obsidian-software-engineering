---
tags:
  - guide
  - reference-notes
  - system-design/case-study
Draft: true
source_url: https://www.hellointerview.com/learn/system-design/problem-breakdowns/fb-news-feed
---


# Requirements
## Functional
1. Users should be able to create posts.
2. Users should be able to friend/follow people.
3. Users should be able to view a feed of posts from people they follow, _in chronological order_.
4. Users should be able to page through their feed.
## Non-functional
- Availability over consistency for news feed
- Low latency <500ms loading of feed for both posting and viewing
- Scalability to handle large amounts of load
# Core Entities
User
Follow
Post
Feed
# API

```
// Follow user
POST /follows - 201
{
  user
}

// Create post
POST /posts - 201
{
   title,
   body
}

// Load feed/posts
GET /feed - 200 - Post[]
```

# High-level Architecture
![[Design Facebook News Feed 2025-08-29 18.06.38.excalidraw]]

# Deep Dives