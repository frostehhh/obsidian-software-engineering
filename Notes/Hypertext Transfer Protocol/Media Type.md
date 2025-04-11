---
tags:
  - backend
  - communication/protocols
  - notes
"Parent:":
  - "[[Hypertext Transfer Protocol|HTTP]]"
aliases:
  - MIME Type
  - Multipurpose Internet Mail Extension Type
---
# Media Type
- Used by Content-Type response header
- Discrete and Multiple types
- For identifying content being sent
	- Why? so that they can be processed according to their types

## Example Usecases
- video or audio types are needed to for "playable" media types
- RAR-compressed file require a specific header to know that they have to be decompressed

# MIME Sniffing
- Browser performs this if the content-type may be incorrect
	- Each browser has different implementations
- `X-Content-Type-Options` header to indicate to receiver to trust the `Content-Type`

## References
https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/MIME_types#mime_sniffing