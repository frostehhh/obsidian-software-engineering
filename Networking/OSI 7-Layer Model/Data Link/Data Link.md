---
aliases: [Layer 2]
---
- Runs over layer 1
- Can run on different types of [[Physical|Layer 1]] networks
- Introduces unique hardware address [[MAC Address]]  - identifiable devices
- Provides physical addresssing
- It transmits [[Frames]]
- Utilizes [[CSMA CD]]
- Can do Unicast communications - 1:1
- Can do Broadcast communications - 1:ALL

> [!note] 
> Two different layer 2 networks must have the same protocol so that they can directly communicate with each other 

### List of some Layer 2 Protocols
- Ethernet
- IEEE 802.11 wireless LAN




### Example
#### CSMA/CD

![[OSI-LAYER2-DATALINK-3.png]]

> [!note] 
> As data is being passed in the OSI model, it is encapsulated in different components (e.g. Transport layer, network layer, data link layer)

#### Layer 2 using a hub
![[OSI-LAYER2-DATALINK-4.png]]
> [!note] 
> A collision domain is a part of a network where packet collisions can occur ([ref](https://study-ccna.com/collision-broadcast-domain/))  

#### Layer 2 using a Switch
![[OSI-LAYER2-DATALINK-5.png]]
A layer 2 network [[Switch]] can be used to  reduce the risk of collisions in a network. In the above example, there are 4 collision domains. In this case, when a collision occurs, not all devices are affected as opposed to the previous example in [[#Layer 2 using a hub]]





### More References
[ManageEngine - Network Monitoring - Layer 2 Protocols](https://www.manageengine.com/network-monitoring/layer-2-protocols.html)