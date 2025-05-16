---
tags:
  - backend
  - notes
Draft: false
---

- Applying versioning to APIs

# When Should You version an API
- Renaming an endpoint
- Making optional params required
- Changing the data structure or format for requests/response
# Versioning Strategies
- URL Versioning - most popular - `/v1/tweet`
- Query parameter versioning
- Header versioning
- Consumer-based versioning
# Benefits
- Provides a structure for API consumers' visibility on API changes
- Avoid unexpected breaking changes for consumers
- Provide a way for consumers to trust our API - we won't suddenly break our API
# How To Apply API Versioning
1. Choose a versioning strategy
2. Identify if a new version is needed
3. Document API changes
4. Release new version
5. Deprecate old version

# References
https://www.postman.com/api-platform/api-versioning/