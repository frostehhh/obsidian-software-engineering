
![[OSI-LAYER4-TRANSORT-2.png]]
- They don't have SRC or DST IPs because they rely on [[Network|Layer 3]] for this
- Because of [[Ports]], you can have multiple streams of communication
- Sequence Number - incremented with each segment that's sent, and it's unique. It can be used for error correction, etc. It is a way of uniquely identifiying a particular segment in a particular connection so that both sides can make observations about it. 
- These observations are done with **Acknowledgements**
- Flags 'n' Things
	- 9 bits
	- Flags are used to close the connection or synchronize sequence numbers, but there's also additional things like data offset and some reserved space
- Window - defines the number of bites that you indicate that you're willing to receive between acknowledgements. Once received, the sender pauses until the receiver acknowledges the data. This is how flow control is implemented. It lets the receiver control the rate at which the sender sends data.
- Checksum - for error checking. Retransmission if there is an error
- Urgent Pointer
	- Valid only if the URG control flag is set
	- Used to point to data that is urgently required that needs to reach the receiving process at the earliest