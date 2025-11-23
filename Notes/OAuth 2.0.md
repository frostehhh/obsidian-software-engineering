---
tags:
  - notes
  - security/authorization
Draft: false
aliases: OAuth
---

- an authorization framework open standard
- Separation of resource server and authorization server
- v1.0 is deprecated

# Entities Involved
- Resource Server
- Resource Owner
- Authorization Server
- Client

# Flow
1. **Client** requests access to **resource owner**
2. **Resource owner** authorizes **client** to request an access token via the **authorization server**
3. **Client** requests access token via the **authorization server**.
4. **Authorization server** authenticates the **client** via the request and if successful, returns the access token
5. Client uses the access token to interact with the **resource server**
6. Resource server verifies validity of access token and returns requested resources.

# References
https://datatracker.ietf.org/doc/html/rfc6749#section-1.1