---
tags:
  - notes
  - computer-science/locks
Draft: false
"opposite:":
  - "[[Pessimistic Locks]]"
---
- No explicit lock created as opposed to [[Pessimistic Locks]]
- Application logic handles the locking mechanism
	- Less resources needed as a result

> [!example] 
>  Include a version column in a database table schema. When updating, ensure the current update and the existing row versions match. If true, continue update and otherwise, prevent update because it has been updated by someone else.

> [!note] 
>  "I will deal with this when the opportunity comes."

