![[Pasted image 20230107180102.png]]

- Types of ports [[Frame Tagging (802.1Q and 802.1AD)|802.1Q]] switches
	- ACCESS ports- communicate with stations using normal ethernet (NO VLAN tagging, VLAN ID is removed from frame)
	- TRUNK ports - connection between two 802.1Q capable devices. Carries all VIDs with TAGGING
- Devices on different VLANs cannot communicate with each other without a [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/Network|Layer 3]] device(router)

- VLANs allow to create separate [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Data Link/Data Link|Layer 2]] network segments
- Isolated traffic isolation

> [!info] 
>  VLANs are how things in AWS such as public and virtual [[Virtual Interface|VIF]]s on [[Direct Connect]] work