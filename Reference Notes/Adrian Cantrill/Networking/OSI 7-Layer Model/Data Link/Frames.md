A frame is a unit of communication in the data link layer. Data link layer takes the packets from the Network Layer and encapsulates them into frames. If the frame size becomes too large, then the packet may be divided into small sized frames. At receiver’ end, data link layer picks up signals from hardware and assembles them into frames.

![[OSI-LAYER2-DATALINK-1.png]]

###### Components
1. Preamble
	- 56 Bits
	- informs the receiving system that a frame is starting and <mark style="background: #FFF3A3A6;">enables synchronisation</mark>.
1. MAC Header
	1. Destination MAC Address
		Can be set to a specification destination or broadcast(All F's)
	2. Source MAC Address
	3. Ethertype(ET) 16 Bits - specifies which layer 3 protocol is putting its data in the frame (e.g. IP)
3. Payload
	Data that the frame carries from source to destination. Generally provided by [[Reference Notes/Adrian Cantrill/Networking/OSI 7-Layer Model/Network/Network|Layer 3]]
	64 - 1500 bytes
4. Frame Check Sequence (FCS)
	Checks if there are any errors
	32 bits

# See Also
[[Jumbo Frames]]

# References
https://study-ccna.com/ethernet-frame/#:~:text=Preamble%20%E2%80%93%20informs%20the%20receiving%20system,MAC%20%E2%80%93%20identifies%20the%20sending%20system.