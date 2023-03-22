---
aliases: [CFN, CloudFormation Basics]
---
![[Pasted image 20230320014948.png]]

# Components
1. Resources
	- All templates have a list of resources
	- Tells CloudFormation what to do
	- When updated, also updated the actual resources created
	- The only mandatory part of a CloudFormation template
2. Description
	- Let's the author add a description as the name implies.
	- **Restriction** - must directly follow the AWSTemplateFormatVersion if it is specified
3. Metadata
	- Controls how the diff things in the CloudFormation template are presented through the console UI if you're applying it
		- Can add grouping, orders, etc.
4. Parameters
	- Prompt user for more information
		- Example: names, default values, etc.
5. Mappings
	- allows to create lookup tables
6. Conditions
	- decision making in a template
7. Outputs
	- A way that once a template is finished, it can show what's being updating, created or deleted


# References
[Adrian Cantril SAA-C03 Course - CloudFormation (CFN) Basics](https://learn.cantrill.io/courses/1820301/lectures/41301626)