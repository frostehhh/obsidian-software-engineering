---
aliases: [802.1Q, 802.1AD, QinQ, Frame Tagging]
---

![[Pasted image 20230107173048.png]]

With this standard we can support VLANs at the layer 2 level

# 802.1Q
Adds a 802.1Q Field with 32 Bits(equivalent to 4 Bytes). Default ethernet frame sizes can be extended to allow for the newly added field

### 802.1AD
- Also called QinQ
- Used for provider bridging/ stacked VLANs
- Adds an additional VLAN field where the 1st is KNOWN as S-TAG (service tag) and the second is C-TAG (customer tag)
- This standard allows ISPs or carriers to use VLANs across their network, while carrying customer traffic which might also be using multiple VLANs

### References
