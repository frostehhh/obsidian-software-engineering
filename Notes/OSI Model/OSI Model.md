---
tags:
  - notes
  - backend/networking
  - backend/communication
Draft: false
aliases:
  - Open Systems Interconnection Model
"related-reference-note:":
  - - Reference Notes/Hussein Nasser/Udemy - Fundamentals of Backend Engineering/Section 3 - Protocls/OSI Model|OSI Model
---

# What is the OSI Model?
The OSI model is a conceptual framework of how communication occurs in software. There are 7 layers
1. Physical - ethernet, Wi-Fi, fiber cables, radio waves
2. Data Link - MAC Address
3. [[Notes/OSI Model/Network|Network]] - IP Address
4. Transport - Ports
5. Session - TLS
6. Presentation - plain text, JSON
7. Application

# Why is this important?
This helps us to further understand the components of communication in relation to communication protocols and the fundamentals of communication in software. With knowledge on this, we can better understand related concepts, have more ease in knowing how things are connected, have a better time with evaluating protocols on our own, etc.

The OSI model provides a standard for hardware to communicate. For instance, for network devices like routers to be able to communicate to each other, they need to be communicating with the same protocols. In this case, routers understand IP Addresses, MAC Addresses and are compatible with transfer mediums such as cables and Wi-Fi. If there were no such a standard, there would need to be an added layer of implementation between 2 devices to understand each other's protocols OR to form a unified way of communicating to each other.

With standards for communication, upgrading network devices to support few standardized protocols is more realistic.
# References
For better reading, see [[OSI 7-Layer Model]]
