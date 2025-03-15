![[Pasted image 20230403003533.png]]
- A feature of AWS Organizations which **allow restrictions to be placed on MEMBER accounts** in the form of boundaries.
- SCPs can be applied to the organization, to OU's or to individual accounts.
- Member accounts can be effected, the MANAGEMENT account cannot.
- SCPs DON'T GIVE permission - they just control what an account CAN and CANNOT grant via identity policies.
- json document

![[Pasted image 20230403003613.png]]

![[Pasted image 20230403003705.png]]
- When SCP is enabled, `FullAWSAccess` policy is available by default
- Deny list by default with the FullAWSAccess rule

![[Pasted image 20230403003719.png]]
Disable or remove FullAWSAccess to convert to allow list

![[Pasted image 20230403003813.png]]