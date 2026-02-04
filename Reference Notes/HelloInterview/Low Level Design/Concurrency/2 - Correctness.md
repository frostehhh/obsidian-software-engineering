---
tags:
  - low-level-design
  - reference-notes
  - synchronization
  - concurrency
Draft: false
source_url: https://www.hellointerview.com/learn/low-level-design/concurrency/correctness
---

# Coarse-grained lock
- A general purpose lock with no specific conditions attached
- It is always used given an operation
- Use when
	- Small and infrequent operations

```java
class TicketBooking {
    private final Object bookingLock = new Object();
    private Map<String, String> seatOwners = new HashMap<>();

    public boolean bookSeat(String seatId, String visitorId) {
        synchronized (bookingLock) {
            if (seatOwners.containsKey(seatId)) {
                return false;
            }
            seatOwners.put(seatId, visitorId);
            return true;
        }
    }
}
```
## Read-Write Lock
- A lock particularly used for heavy reads and infrequent writes
- Example: Use for cases where
# Questions
- java synchronized block