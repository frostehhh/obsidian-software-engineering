![[Pasted image 20230402184740.png]]
**Standard Account** - AWS account that's not in an organization
Use standard account to create an organization. This account bcomes the management account(previously master account) for the organization

**Organizational Unit (OU)** - container for accounts. Can contain other OUs

**Member accounts** - member accounts of an organization. 

![[Pasted image 20230402185109.png]]
**Consolidated billing**. Only management account is responsible for paying billing

**Can also create new accounts directly within organization**. Need only valid email address. No need for invite process.

![[Pasted image 20230402190439.png]]
- **No need to have an IAM user for every AWS account**. Can utilize just IAM roles instead
- Can have a separate AWS account in an organization for logins
- Can use identity federation
	- For example, use identities from on-premises
- Assign roles to authenticated users so that they can work with AWS accounts in the organization

# Related
[AWS Whitepaper -  Organizing Your AWS Environment Using Multiple Accounts](https://docs.aws.amazon.com/whitepapers/latest/organizing-your-aws-environment/organizing-your-aws-environment.html)
[AWS Organizations terminology and concepts](https://docs.aws.amazon.com/organizations/latest/userguide/orgs_getting-started_concepts.html)