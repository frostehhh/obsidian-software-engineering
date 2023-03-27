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


# References
[AWS Documentation - IAM Roles](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles.html)