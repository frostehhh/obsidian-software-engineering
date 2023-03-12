---
aliases: [DNS]
---


![[DNS101-1.png]]

DNS converts DNS names into IP addresses

# Key Terms
![[Pasted image 20230108041939.png]]

# Hierachical Design
![[DNS101-4.png]]
## Root zone
- 13 root servers managed by organizations
- a database assigned by IANA
- management by the root zone and root servers is not IANA
- contains high level information on the high level info on TLDs
- Points to TLD registries

## Top Level Domains (TLD)
- Types of TLD
	- generic like .com
	- country code like .au
- IANA delegates management of TLDs to other organizations known as registries
- Points to authoritative name servers

## Authoritative Name Servers
- Contain at least 1 zones for domains
- Each zone has a corresponding Zone and ZoneFile