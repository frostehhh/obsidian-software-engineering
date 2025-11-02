---
tags:
  - notes
  - networking
Draft: true
related-reference-note:: 
  - "[[Reference Notes/Github - donnemartin system-design-primer/Domain Name System|Domain Name System]]"
  - "[[Reference Notes/Adrian Cantrill/Networking/Domain Name System/Domain Name System|Domain Name System]]"
---

A Domain Name System (DNS) translates a domain name such as [www.example.com](http://www.example.com/) to an IP address.
- hierarchical - there are authoritatize servers at the top level

# Terminologies
- Root Name Server - a top-level name server
- Top-level Domain - a name server for top-level domains. Top-level domains refer to the text after the last dot. Ex. `com`, `web`, `ai` 
- NS - Name server
- MX - Email exchange record. Indicates server for where messages are sent and received.
- A - Address record. ex. 12.1.2.54
- CNAME - Canonical name record.

# Mechanisms for DNS Server Allocation
- Weighted Round-Robin - formula for weights is applied to each server as a form of scoring. This dictates the order of the server returned by the round robin mechanism. Weight is typically based on the amount of load each server can handle. Ex. A server with level 2 power will take twice as much requests as a server with level 1 power.
- Latency-based
- Geolocation-based


# How A DNS Request Travels
See [[What do we want from DNS#Walking the tree]]
