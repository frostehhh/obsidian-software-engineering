---
tags:
  - notes
  - backend
  - communication/protocols/http
Draft: false
"Parent:":
  - "[[Hypertext Transfer Protocol|HTTP]]"
has-questions: true
---
- Data
- Purpose
	- session management - sessionIDs, [[Notes/JSON Web Token|JSON Web Token]]
	- user preferences - theme(dark mode or light mode)
	- tracking
- Client shouldn't modify this
- Removable via
	- Expiry datetime
	- Max age
- Can be used to prevent Cross-site request forgery via `SameSite`
- Cookies are set via `SetCookie` [[Hypertext Transfer Protocol|HTTP]] Header
# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Cookie

# Questions
- Difference between cookies and local storage and session storage?

# Anki