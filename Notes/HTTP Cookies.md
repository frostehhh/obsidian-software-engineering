---
tags:
  - notes
  - backend/communication
Draft: false
"Parent:": "[[Hypertext Transfer Protocol|HTTP]]"
has-questions: true
---
- Data that contains info that may be any of the following purposes mainly:
	- session management - sessionIDs, [[Notes/JSON Web Token|JSON Web Token]]
	- user preferences - theme(dark mode or light mode)
	- tracking
- Client should not be able to modify this data
- Primarily used in HTTP communication
- Can set removal of cookie via
	- Expiry datetime
	- Max age
- Can be used to prevent Cross-site request forgery via `SameSite`
- Cookies are set via `SetCookie` [[Hypertext Transfer Protocol|HTTP]] Header
# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Cookie

# Questions
- Difference between cookies and local storage and session storage?
- 