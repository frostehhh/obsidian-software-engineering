---
tags:
  - database
  - notes
Draft: false
"related-reference-note:":
  - "[[Reference Notes/Hussein Nasser/Udemy - Fundamentals of Database Engineering/Section 2 - ACID/Isolation|Isolation]]"
"Parent:": 
 - "[[ACID]]"
---

Database transactions must run independent of other transactions
# Read Phenomena
Related to the concept of isolation, below are problematic scenarios that may occur
## Dirty Read
Read uncommitted changes from a different transaction
## Non-repeatable Read
- Read committed changes from a different transaction
- Non-repeatable because the same read repeated gives different results. Hence, it is non-repeatable

## Phantom Read
Read committed inserts from a different transaction

## Lost updates
With two different transactions where both update the same row, one will overwrite the other.

# Isolation Levels
- Read uncommitted - transactions can read each other's changes
- Read committed - a transaction can read commits from other transactions
- Repeatable read - a transaction's reads are kept as a snapshot
- Snapshot - A snapshot of data are stored at the beginning of the transaction
- Serializable - transaction are run as if in a linear manner

> [!info] 
>  There are different implementations for these for each different DBMS

![[Isolation Levels vs read phenomena.png]]

# Database Implementation for Isolation
- Pessimistic locking
- Optimistic locking
- Repeatable reads
- Serializable
## Pessimistic locking
- Uses locks to ensure no other transactions will write over a transaction's changes
- Pessimistic in the sense that we have a mechanism set up eagerly to prevent unexpected changes
## Optimistic locking
- Deal with dirty updates or reads that moment you see them
- Can implement this in update scenarios by having a version int column in data rows. The version is incremented on update.
## Repeatable reads
- Read rows are snapshotted(this is done by Postgres)
# Serializable
- Usually implemented with optimistic locking due to expensive resources needed for pessimistic locking
- If pessimistic locking, can use `SELECT FOR UPDATE`
# References
https://learn.microsoft.com/en-us/sql/odbc/reference/develop-app/transaction-isolation-levels?view=sql-server-ver16
