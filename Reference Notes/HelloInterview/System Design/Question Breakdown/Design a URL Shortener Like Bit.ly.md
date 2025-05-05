---
tags:
  - guide
  - reference-notes
  - system-design/case-study
draft: true
source_url: https://www.hellointerview.com/learn/system-design/problem-breakdowns/bitly
---


# Requirements
## Functional
1. Users should be able to submit a long URL and receive a shortened version.
    - Optionally, users should be able to specify a custom alias for their shortened URL.
    - Optionally, users should be able to specify an expiration date for their shortened URL.
2. Users should be able to access the original URL by using the shortened URL.
## Non-functional
1. The system should ensure uniqueness for the short codes (no two long URLs can map to the same short URL)
2. The redirection should occur with minimal delay (< 100ms)
3. The system should be reliable and available 99.99% of the time (availability > consistency)
4. The system should scale to support 1B shortened URLs and 100M DAU

# Core entities
- Original URL
- Short URL
- user
# API

# High-Level Architecture
# Deep Dives
# Notes
301 redirect - permanent
302 redirect - temporary

base62 encoding
# Questions
read-after write consistency - read immediately after writing
redis