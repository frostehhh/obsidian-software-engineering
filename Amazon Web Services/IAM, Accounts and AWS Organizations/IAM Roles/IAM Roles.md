![[Pasted image 20230327063143.png]]
- Similar to an [[IAM Users|IAM User]], but instead, it can be associated to multiple entities. It is intended to be assumable by anyone who needs it.

# Supported Policies
![[Pasted image 20230327070844.png]]
> [!info] 
>  STS refers to the AWS Security Token Service
## Trust Policy
- Can reference identities in the same AWS account and other AWS accounts
- Can allow anonymous usage
- Can allow entities like Facebook, Google, etc.
## Permissions Policy

# When to use IAM Roles

## AWS Service
![[Pasted image 20230402034039.png]]
- AWS Lambda
	- Lambda execution role trusts Lambda Service
![[Pasted image 20230402034425.png]]
- Emergency situations

## Existing Corporate Environment
![[Pasted image 20230402034904.png]]
existing corporate environment
existing physical network
existing identity provider
External accounts can't be used in AWS directly - Facebook, google, etc. identities

> [!info] 
>  Identity Federation - giving permissions to external identity provider and allowing them to assume an AWS role

## Customer Usage
![[Pasted image 20230402040759.png]]
Can assign a role to a common user for 
access to an AWS service

## Cross-account usage
![[Pasted image 20230402040943.png]]
Users in AWS Account A can be assigned a Role to access resources in AWS Account B

# See Also
[[Service-linked Roles]]

# References
[AWS Documentation - IAM Roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)