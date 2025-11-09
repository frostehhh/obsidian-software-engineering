---
tags:
  - notes
  - aws/sqs
Draft: true
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