# Network-Protocols

### TCP
TCP - Transmission Control Protocol, this protocol is responsible for making sure packets get where they are supposed to go. It deals with duplicate packets, lost packets, etc. It also is responsible for authentication through the 3 way handshake. SYN: The client sends a segment with the SYN (Synchronize Sequence Number) flag set to the server, indicating that it wants to start communication and specifying the sequence number it will use for its segments1.
SYN-ACK: The server responds to the client’s request with a segment that has both the SYN and ACK flags set. The ACK flag acknowledges the receipt of the client’s SYN segment, while the SYN flag indicates the sequence number that the server will use for its segments1.
ACK: The client sends a final segment with the ACK flag set to acknowledge the receipt of the server’s SYN-ACK segment. At this point, both the client and server have synchronized their sequence numbers and established a reliable connection, allowing them to begin transmitting data.

Protocol suite - a set of protocols designed to work together. TCP/IP For example.

![image](https://github.com/derekrjohnson/Network-Protocols/assets/142181223/30d776cb-117d-4c29-b39e-7cff6cfdbd2d)

TCP has responsibility to ensure a secure connection at the session layer with the 3 way handshake.


### ARP
Carrier Sense Multiple Access With Collision Detection - Computers wait a random duration of time to send messages over the wire again after a collision occurs.

First 3 bytes of Ethernet header tells you who manufactored the network interface card.

ARP - Adress resolution protocol, who has this IP? This broadcast is sent out to the entire LAN. 

![image](https://github.com/derekrjohnson/Network-Protocols/assets/142181223/57f867ef-50df-4ee9-9443-837456a1af11

ARP broadcasts clutter the netowrk, and is inefficent. This is why ARP information is cahched by the systems on the LAN both endpoints and routers.

### MAC Spoofing

MAC addresses are meant to be "unique," but they're actually
easily changed and rarely verified. What problems could this
cause?

* Bypass MAC-based network access controls
* Switches and/or Wireless AP’s may restrict access to registered MACs only
* Impersonating another user/system
* Harder to trace actions back to user/system
* Denial of Service
* Can cause network issues and potentially prevent access to system being spoofed  direct Traffic
* Spoofing default gateway or server can result in traffic being redirected to attacker

### Arp Spoofing

* A malicious actor sends falsified ARP (Address Resolution Protocol) messages over a local area network.
* This results in the linking of an attacker’s MAC address with the IP address of a legitimate computer or server on the network.
* The attacker’s MAC address will begin receiving any data that is intended for that IP address.
* ARP spoofing attacks can only occur on local area networks (within layer 2 Broadcast Domain)

![image](https://github.com/derekrjohnson/Network-Protocols/assets/142181223/c22679e5-d9af-45d2-90d4-6ccbc57bb3f2)

![image](https://github.com/derekrjohnson/Network-Protocols/assets/142181223/4baa6507-0d1e-48c8-a502-136a85024418)

### NAT

When a packet of data is leaving a Local Area Network, the private destination IP won't work to resolve a response. To solve this the last router before data leaves the LAN uses NAT Network Address Translation to assign the source a public facing address. NAT stops data transformation from going directly to a private address/system.

### NAT - IP Masquerading 

### PAT - Port address translation

The router starts going to layer 4 to rewrite the internal port.

### IPv6

IPV6 occupies 128 bytes. Leading zeros can be ommitted and it is represented with ::. You can only use the :: once to represent zeros. 
No broadcast address, makes DHCP and ARP hard. Netowrk discovery is used instead of ARP. 
fe80:: is considered to be local.
48 bits for router prefix, 16 bits subnet id, 64 bits for interface ID.
![image](https://github.com/derekrjohnson/Network-Protocols/assets/142181223/eb51e3e5-9192-454e-a149-6fa217f96b5b)

### Lab 7-1 Notes

Creating an address pool in packet tracer.
```Router(config)#ip nat pool champ 216.93.144.10 216.93.144.10 netmask 255.255.255.0```

Creating an access-list in packet tracer.
```Router(config)#access-list 1 permit 192.168.0.0 0.0.255.255```

Finally, run the following command which tells the router any 192.168 addressw will be translated to 216.93.144.10 when packets leave the LAN.
```Router(config)#ip nat inside source list 1 pool champ overload```

### Mid term review
What protocol uses link state?
OSPF - Open shortest path first.















