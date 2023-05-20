---
aliases: [CloudWatch Basics]
---
# Summary
CloudWatch Logs is a service which can accept logging data, store it and monitor it.

It is often the default place where AWS Services can output their logging too.

CloudWatch Logs is a public service and can also be utilised in an on-premises environment and even from other public cloud platforms.

# Details

![[Pasted image 20230326033200.png]]
- Allows metrics, monitoring of metrics and actions based on metrics
- CloudWatch Logs - Allows logs, monitoring of logs and actions based on logs
- CloudWatch Events - real-time stream of system events that describe changes in Amazon Web Services

![[Pasted image 20230326033237.png]]
Statistics can be viewed via console or API. Alarms can be used to take actions like auto-scaling EC2 instances

# Related Concepts
[[Metrics]]
[[Namespace]]
[[Alarms]]

# References
[What is Amazon CloudWatch Events?](https://docs.aws.amazon.com/AmazonCloudWatch/latest/events/WhatIsCloudWatchEvents.html)