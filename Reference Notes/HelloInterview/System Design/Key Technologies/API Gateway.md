---
tags:
  - reference-notes
  - backend
  - system-design
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/api-gateway
Draft: false
---


- Mainly for routing requests
# Functions
## Request Validation
- Check if the request is valid
- Example
	- is request body valid
	- are required headers included
	- is API version specified

## Middleware
- Includes but not limited to the following functionalities:
	- authentication
	- rate-limiting
	- 


## Request Routing
- Checks request info to determine where to pass request
	- path
	- request method
	- headers

## Backend Communication
- Can transform request to be compatible with communication protocol used
	- Prevents coupling with client's communication protocol
## Response Transformation
- Transform response from application server to desired format by client
- Example: Transform gRPC response to JSON
## Caching
- Cache response if desired
- Typically, not user-specific responses

# API Gateway in System Design
- Typically, necessary for microservices
- Can simply mention that it is for request routing and basic middleware

# Scaling
Either
- horizontally
- global distribution