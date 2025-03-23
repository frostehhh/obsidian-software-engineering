---
tags:
  - notes
  - operating-system
Draft: false
related-reference-note::
- "[[The Process and the Thread and how they compete for CPU time]]"
Parent:: "[[Process]]"
---
- A Light-weight [[Process]](LWP)
- Shares memory with main [[Process]]

# Cons
- Shared memory with main process
- Race conditions with other threads thus requiring locking

# When do you use Threads?
- Need to run a separate task asynchronously
- Heavy CPU usage task
- Need to run large amount of small tasks
