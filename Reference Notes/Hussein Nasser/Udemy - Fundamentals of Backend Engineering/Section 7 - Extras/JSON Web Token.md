---
tags:
  - reference-notes
  - backend/security/authentication
Draft: true
---

![[Session-based Authentication]]
# JWT
- A authentication token used to contain the state of authentication of a user. It contains the data, headers and secret.
## Pros
- Simple
## Cons
- When the token gets stolen, there is nothing that can be done to revoke the authentication token and prevent the bad actor to keep using the token.

## Refresh Token
This token makes it so that we can expire the token every x interval. When