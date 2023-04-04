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
- A [JSON policy document](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_grammar.html) in which you define the principals that you _trust_ to assume the role. A role trust policy is a required [resource-based policy](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html#policies_resource-based) that is attached to a role in IAM. The [principals](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies_elements_principal.html) that you can specify in the trust policy include users, roles, accounts, and services.
## Permissions Policy
- A permissions document in [JSON](http://www.json.org/) format in which you define what actions and resources the role can use. The document is written according to the rules of the [IAM policy language](https://docs.aws.amazon.com/IAM/latest/UserGuide/reference_policies.html).

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
[AWS IAM Roles terms and concepts
](https://docs.aws.amazon.com/IAM/latest/UserGuide/id_roles_terms-and-concepts.html)