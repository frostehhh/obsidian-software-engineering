- Every router has at least 1 route table
- Router compares packet destination IP & route table for matching destinations
- Route tables can either be statically populated or automatically populated via the [[Border Gateway Protocol]] (BGP)
- [[Address Resolution Protocol]] is used when you have a layer 3 packet and you want to encapsulate it inside a frame and then send that frame to a MAC address

### Example

![[OSI-LAYER3-NETWORK-5.png]]
> [!note] 
>  0.0.0.0/0 in the routing table is a default route in case a destination IP address doesn't match any other record 