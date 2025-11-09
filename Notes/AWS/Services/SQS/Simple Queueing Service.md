---
tags:
  - notes
  - aws/sqs
Draft: false
aliases:
  - SQS
  - AWS SQS
"Friend:":
  - "[[Message Queue]]"
  - "[[Simple Notification Service|SNS]]"
---

- AWS Message queue
- Types of queues
	- Standard
	- FIFO
- Visibility Timeout - timer until message will be visible when querying the queue messages

# Sample Usage Flow
1. Producer creates message A and stores into SQS distributed nodes
2. Consumer A consumes message A and marks as invisible. Visibility timeout timer starts
3. Consumer A deletes message A from SQS queue after accomplishing job.
# Queue Types
## Standard
- at least once delivery - may have duplicates due to retries and network failures
- for higher throughput
## FIFO
- exactly once delivery
- for strict ordering of messages

# Dead-letter Queues
- Storage of failed messages
- Default retention period of 30 days
- Stores messages failed after default of 2 retries
- Can be redrived to be placed back to the main queue
- If messages are added to this queue, it is likely due to an issue with the workers: bugs or downtime.