---
tags:
  - guide
  - reference-notes
  - low-level-design/case-study
Draft: false
date: 2026-01-05
"origin:": "[[Design Rate Limiter]]"
---

> [!note]
> Didn't complete, but considered done enough for practice

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
	Limiter defaultConfig;
	
	public RateLimiter(configs, defaultConfig)
}


interface Limiter {
	public RateLimitResult allow(clientId, endpoint)
}

// Create 
class LimiterFactory {
	public Limiter create(externalConfig) {}
}
class TokenBucketLimiter implements Limiter {}
class SlidingWindowLogLimiter implements Limiter {}

class RateLimitResult {
	boolean allowed;
	int remaining;
	long retryAfterMs; // nullable
}
```

# Implementation
```java
class RateLimiter {
    // endpoint to configuration
	Map<String, Limiter> configMapping;
	Limiter defaultConfig;
	
	
	// configs and defaultConfig are json
	public RateLimiter(
		List<Map<String, Config>> configs,
		Map<String, Config> defaultConfig,
	) {
		LimiterFactory factory = new LimiterFactory();
		Map<String, Limiter> newLimiters = new HashMap<>();
		for (Map<String, Config> externalConfig : configs) {
			String endpoint = externalConfig.get('endpoint');
			Limiter limiter = factory.create(externalConfig);
			newLimiters.set(endpoint, limiter);
		}
		
		this.configMapping = newLimiters;
		this.defaultConfig = JSON.parse(defaultConfig);
	}
}

interface Limiter {
	public RateLimitResult allow(clientId, endpoint)
}
// Create 
class LimiterFactory {
	public Limiter create(externalConfig) {
		string algorithm = externalConfig.get('algorithm');
		JSONObject algoConfig = externalConfig.get('algoConfig');
		
		switch (algorithm) {
			case "token_bucket": {
				return TokenBucketLimiter(
				)
			}
			case "sliding_window_log": {
				return SlidingWindowLogLimiter(
				);
			}
			default: {
				throw new RuntimeException("Unknown algorithm");
			}
		}
		
	}
}
class TokenBucketLimiter implements Limiter {
	// private state that I do not know. Specific to this limiter

	public RateLimitResult allow(String key) {
	
		return RateLimitResult(...)
	}
class SlidingWindowLogLimiter implements Limiter {
	public RateLimitResult allow(String key) {
	
		return RateLimitResult(...)
	}
}

class RateLimitResult {
	boolean allowed;
	int remaining;
	long retryAfterMs; // nullable
}
```

## SampleFlow
```java
//initialize



RateLimiter rl = new RateLimiter(configs, defaultConfig);

```

# Extensibility and Maintainability
