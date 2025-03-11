---
tags:
  - reference-notes
---
# High-level trade-offs
- **Performance** vs **scalability**
- **Latency** vs **throughput**
- **Availability** vs **consistency**

# Performance vs Scalability
A service is **scalable** if it results in increased **performance** in a manner proportional to resources added.

> [!NOTE] Alternative perspective
> Slow performance = slow for a single user. Bad scalability = slow for many users

Why is scalability so hard? Because scalability cannot be an after-thought. It requires applications and platforms to be designed with scaling in mind, such that adding resources actually results in improving the performance or that if redundancy is introduced the system performance is not adversely affected.
# Latency vs throughput
**Latency** is the time to perform some action or to produce some result. **Throughput** is the number of such actions or results per unit of time. Generally, you should aim for **maximal throughput** with **acceptable latency**.

## Example
The latency is: 8 hours.
The throughput is: 120 cars / day or 5 cars / hour.


# Availability vs consistency
In a distributed computer system, you can only support two of the following guarantees. This is known as the CAP Theorem:

- **Consistency** - Every read receives the most recent write or an error
- **Availability** - Every request receives a response, without guarantee that it contains the most recent version of the information
- **Partition Tolerance** - The system continues to operate despite arbitrary partitioning due to network failures

# Consistency patterns
1. Weak consistency
2. Eventual consistency
3. Strong consistency

# Availability patterns
## Fail-over
### Types
#### Active-passive
Also referred to as master-slave failover. Active server is main server and will handover main server role to passive server in case of interruption.
#### Active-active
Also referred to as master-master failover. Both servers are active and managing traffic. Load is balanced between them.

### Disadvantages
- Hardware and additional complexity
- Potential loss of data

## Replication
## Types
### Master-slave
### Master-master


# Availability in numbers
Availability is often quantified by uptime (or downtime) as a percentage of time the service is available. Availability is generally measured in number of 9s--a service with 99.99% availability is described as having four 9s.

# Availability in parallel vs in sequence
A service's overall availability depends on whether the components are in sequence or in parallel.

