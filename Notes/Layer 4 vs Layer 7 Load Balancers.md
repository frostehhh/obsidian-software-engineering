---
tags:
  - reference-notes
  - backend
Draft: false
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 6 - Proxying and Load Balancing/Layer 4 vs Layer 7 Load Balancers]]"
---

# Layer 4 Load Balancer
Only looks at Layer 4 protocol, IP Addresses and ports

## Pros
Simple
Efficient
More Secure
Works with any protocol
One TCP Connection
## Cons
No smart load balancing
NA microservices
Sticky per connection
No caching
Protocol unaware
Does not check content


# Layer 7 Load Balancer
Checks the Layer 7 protocol

## Pros
- Smart Load balancing
- caching
- great for microservices
- API Gateway logic
- Authentication
## Cons
- Expensive looks at data
- Decrypts (terminates TLS)
- Two TCP Connections
- Must Share TLS certificate
- needs to buffer
- Needs to understand layer 7 protocol