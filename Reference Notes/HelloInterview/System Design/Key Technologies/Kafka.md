---
tags:
  - reference-notes
  - backend
  - system-design
  - tool
source_url: https://www.hellointerview.com/learn/system-design/deep-dives/kafka
Draft: true
has-questions: true
---

Apache Kafka is a distributed event streaming platform


# Terminologies and Components
## Broker
Server containing partitions that producers send messages to and consumers consume from
## Topic
Logical grouping of partitions
## Partition
Individual storage of message queue. append-only log file
## Producer
writes messages to partitions
## Consumer
reads messages from partitions. Only 1 consumer per partition
## Message
- default, 1mb max
- No message number limit
- No max message size limit
# Basic flow
## Creation of Message
Structure
- Headers - includes metadata that can be used for various purposes
- Key - also the partition key
- Value
- Timestamp
## Sending of message to a topic
- Includes partition key?
	- yes
		- hash(key) % N to get partition
	- no
		- round-robin or other logic
- Assignment of message to partition

## Consumption of messages

```mermaid
sequenceDiagram
Consumer->>Kafka: Read last message given offset
activate Kafka
Kafka-->>Consumer: Return message
deactivate Kafka

loop Periodically
	Consumer->>Kafka: Send last read offset
end


```

# Use cases
1. Asynchronous processing
2. Large number of requests to process - tickets, messages
3. streams

# Kafka in System Design Interview
## Scalability
- Keep messages sizes within 1mb
- good partition key designs - avoid hot partitions
## Durability
- replica count
- ack config
	- Should all replicas ack before continuing processing or X acks or fully eventually consistent?
## Errors and failures
- Alongside a main topic, have a retry topic and a dead-letter queue(DLQ) topic
## Performance optimizations
- Producer can batch messages to send
- compress messages prior to sending
## Retention Policy
- specify time until messages are cleaned up

# Questions

- What is the AWS equivalent
- How does kafka know that committing of a message has failed?
- retry topic and DLQ topic?