---
aliases: [CloudTrail Basics]
---
# Summary
CloudTrail Is a product which logs API calls and account events.

It's very often used to diagnose security or performance issues, or to provide quality account level traceability.

It is enabled by default in AWS accounts and logs free information with a 90 day retention.

It can be configured to store data indefinitely in S3 or CloudWatch Logs.

# Details

![[Pasted image 20230403023741.png]]
- **Regional Service**
- By default
	- Only **management events** are logged by default
	- **Data events** are not enabled by default
	- No S3 usage

![[Pasted image 20230403025749.png]]
- A trail can be created for a specific region or for all regions(ex. global services events)
- Trail data can be stored in S3
- Can create organizational trail(shown as aws logo in screenshot above). This trail can store all info from all accounts in the organization
![[Pasted image 20230521034744.png]]

# References
[CloudTrail Concepts](https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-concepts.html)