---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: false
date: 2026-01-05
"origin:": "[[Design Rate Limiter]]"
---

# Problem

"You're building an in-memory rate limiter for an API gateway. The system receives configuration from an external service that provides rate limiting rules per endpoint. Each endpoint can have its own limit with a specific algorithm. Here's an example configuration for one endpoint:

```
{
  "endpoint": "/search",
  "algorithm": "TokenBucket",
  "algoConfig": {
    "capacity": 1000,
    "refillRatePerSecond": 10
  }
}
```

This config allows bursts up to 1000 requests, refilling at 10 requests per second.

Your job is to build the in-memory rate limiter that enforces these rules."

# Requirements
1. Configuration is provided at startup (loaded once)
2. System receives requests with (clientId: string, endpoint: string)
3. Each endpoint has a configuration specifying:
   - Algorithm to use (e.g., "TokenBucket", "SlidingWindowLog", etc.)
   - Algorithm-specific parameters (e.g., capacity, refillRatePerSecond for Token Bucket)
4. System enforces rate limits by checking clientId against the endpoint's configuration
5. Return structured result: (allowed: boolean, remaining: int, retryAfterMs: long | null)
6. If endpoint has no configuration, use a default limit

Out of scope:
- Distributed rate limiting (Redis, coordination)
- Dynamic configuration updates
- Metrics and monitoring
- Config validation beyond basic checks

# Entities and Relationships
RateLimiter
Limiter
Endpoint
Client
RateLimitResult
# Class Design

```java
class RateLimiter {
    // endpoint to configuration
	Map<String, Limiter> configMapping;
	
	public RateLimiter(configs, defaultConfig)
}

interface Limiter {
	public RateLimitResult allow(clientId, endpoint)
}

class RateLimitResult {
	boolean allowed;
	int remaining;
	long retryAfterMs;
}
```

# Implementation

# Extensibility and Maintainability
