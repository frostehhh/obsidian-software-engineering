---
aliases: [CFN, CloudFormation Basics]
---
![[Pasted image 20230320014948.png]]

# Components
1. Resources
	- All templates have a list of resources
	- Tells CloudFormation what to do
	- When updated, also updated the actual resources created
	- **The only mandatory part of a CloudFormation template**
	- Referenced via [[Resource Type Identifiers]]
1. Description
	- Let's the author add a description as the name implies.
	- **Restriction** - must directly follow the AWSTemplateFormatVersion if it is specified
2. Metadata
	- Controls how the diff things in the CloudFormation template are presented through the console UI if you're applying it
		- Can add grouping, orders, etc.
3. Parameters
	- Prompt user for more information
		- Example: names, default values, etc.
4. Mappings
	- allows to create lookup tables
5. Conditions
	- decision making in a template
6. Outputs
	- A way that once a template is finished, it can show what's being updating, created or deleted


![[Pasted image 20230322091715.png]]
- Templates create stacks which are then used to create physical resources in an AWS account

![[Pasted image 20230322092103.png]]
- Can be used to quickly spinup cloud deployments
- Can be easily reviewed before deployment

# References
[Adrian Cantril SAA-C03 Course - CloudFormation (CFN) Basics](https://learn.cantrill.io/courses/1820301/lectures/41301626)
[AWS CloudFormation concepts](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/cfn-whatis-concepts.html)
