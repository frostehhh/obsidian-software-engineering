---
aliases: [Route53 Basics, Route53, R53]
---
![[Pasted image 20230326200313.png]]
- AWS's DNS product
- Register domains 
- Host zones on managed nameservices
- Global service ... single database
	- Globally Resilient

# Register Domains
![[Pasted image 20230326201519.png]]
- Route53 has relationship with all major domain registries
- PIR is a company that maintains the registry for the .org domain

# Hosted Zones
![[Pasted image 20230326201905.png]]
- Zone files in AWS
- hosted on four managed name servers
- Can be public
- Or private .. linked to VPC(s)
- stores records (recordsets)

# See Also
[[DNS Record Types]]
[[Supported DNS Record Type]]