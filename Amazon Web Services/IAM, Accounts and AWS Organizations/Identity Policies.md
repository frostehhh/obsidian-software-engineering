# IAM Policy Document
![[Pasted image 20230327003058.png]]
- Written in JSON Format
- At least 1 statement

## Statement components
1. Statement ID (Sid) - optional field that identifies a field and what it does
2. Resource 
	- Referred via [[Amazon Resource Name|ARN]]
	- Can use wildcards(\*)
3. Action
	- Action that can be performed with a resource
	- For example - [Actions supported by IAM](https://docs.aws.amazon.com/IAM/latest/APIReference/API_Operations.html)
 4. Effect
	- Either ALLOW or DENY
	- Describes whether the specified actions is allowed or denied on the given resource

# Example
![[Pasted image 20230327003352.png]]
# Statement priorities
1. Explicit DENY
2. Explicit ALLOW
3. Default DENY (Implicit)

# Example with multiple policies
![[Pasted image 20230327003607.png]]
- If a user has multiple policies, they're all collected and same rules apply

# Example about setting duplicate policies for multiple users
![[Pasted image 20230327003949.png]]
1. Inline policy - assigned to each individual user
2. Managed Policy - reusable policy

# Types
1. [AWS managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#aws-managed-policies)
2. [Customer managed policies](https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html#customer-managed-policies)