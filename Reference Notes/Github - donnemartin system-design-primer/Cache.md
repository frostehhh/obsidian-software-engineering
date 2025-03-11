---
tags:
  - reference-notes
---

Caching improves page load times and can reduce the load on your servers and databases. In this model, the dispatcher will first lookup if the request has been made before and try to find the previous result to return, in order to save the actual execution.

## Different ways to cache
- Client caching
- CDN caching
- Web server caching
- Database caching
- Application Caching

## Examples of data to catch
- User session
- Fully rendered web pages
- Activity streams
- User graph data

## When to update the cache
- cache-aside
	- an application checks the cache before interacting with the database
- write-through
	- Always update cache resulting to consistently slow updates but faster reads\
- write-behind
- refresh-ahead
# References
https://github.com/donnemartin/system-design-primer?tab=readme-ov-file#cache