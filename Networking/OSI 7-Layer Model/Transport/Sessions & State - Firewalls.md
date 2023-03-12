![[OSI-LAYER4-TRANSORT-5.png]]

## Types of Firewall States
### Stateless Firewall
- A TCP connection needs 2 rules - outbound and inbound
- All packets are analyzed in isolation
> [!info] 
> In AWS, the Network ACL utilizes this concept

### Stateful Firewall
- Allowing the outbound implicitly allows the inbound response
> [!info] 
> In AWS, this is how a security group works 

# See Also

[[Stateful vs Stateless Firewalls]]