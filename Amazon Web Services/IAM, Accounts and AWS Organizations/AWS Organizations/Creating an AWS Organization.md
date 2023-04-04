# Adding an AWS account to an organization
To add an AWS account to an organization, we can do either of the following:
- Invite an existing AWS account
- Create a new account under the organization

> [!note] 
> If you invite an existing AWS account to an organization, you need to manually create a role within the invited AWS account that'll allow the organization to access that account. 
> 
> By default when an AWS account is created in an organization, this role is called OrganizationAccountAccessRole. So, we can also define the role this way when we need to manually create the role with an invited AWS account
> 

# Related Course Demo
https://learn.cantrill.io/courses/aws-certified-solutions-architect-associate-saa-c03/lectures/41301371