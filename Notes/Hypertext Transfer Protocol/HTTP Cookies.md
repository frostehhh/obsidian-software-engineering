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
- State Storage
- `Set-Cookie` and `Cookie`
- Purpose
	- session management - sessionIDs, [[Notes/JSON Web Token|JSON Web Token]]
	- user preferences - theme(dark mode or light mode)
	- tracking
- Browser can create, modify and send cookies
	- For safety reasons, better to avoid creation/modification on client
- Removable via
	- Expiry datetime
	- Max age
- Can be used to prevent Cross-site request forgery via `SameSite`
- Cookies are set via `SetCookie` [[Hypertext Transfer Protocol|HTTP]] Header
```
Set-Cookie: id=a3fWa; Expires=Thu, 21 Oct 2021 07:28:00 GMT; Secure; HttpOnly; Path=/docs
```
# References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Cookie

# Questions
- Difference between cookies and local storage and session storage?

# Anki