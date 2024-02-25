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
