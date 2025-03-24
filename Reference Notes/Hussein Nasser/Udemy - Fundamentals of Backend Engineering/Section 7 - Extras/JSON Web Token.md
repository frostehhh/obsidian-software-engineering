---
tags:
  - reference-notes
  - backend/security/authentication
Draft: true
"related:":
  - "[[HTTP Cookies]]"
has-questions: true
knowledge-confidence-level:
  - 2 - Needs improvement
---

![[Session-based Authentication]]
# JWT
- A authentication token used to contain the state of authentication of a user. It contains the data, headers and signature.
- The token is created in the server via encryption of user session data with a symmetric key. The same key is used for decrypting.
- Each service should have access to the same symmetric key for decryption and encryption.
## Pros
- Simple
## Cons
- When the token gets stolen, there is nothing that can be done to revoke the authentication token and prevent the bad actor to keep using the token.

## Refresh Token
This token makes it so that we can expire the token every x interval. When this token exists, the access token includes the expiration datetime in itself. The refresh token also has an expiration datetime but it is valid for a longer period.

## Flow with Refresh Token
1. User sends a POST request to login successfully
2. Server returns access token and refresh token
3. User can repeatedly use the access token and include in requests sent to server
4. When the user receives an "access token expired" error from the server after sending a request, the client should request another access token using the refresh token.
	- If the refresh token is invalid, the client may need to reauthenticate
	- On successful refresh, the refresh token may also be updated

# JWT Secret Sharing
When all services need to share the same symmetric key for auth, it can be dangerous when an attacker steals this via secret sharing.

# Asymmetric JWT

# Questions
- Where does the client store the token/s? 
- How does the client include the tokens in each request?
