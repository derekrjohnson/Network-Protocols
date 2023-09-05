# Network-Protocols
TCP - Transmission Control Protocol, this protocol is responsible for making sure packets get where they are supposed to go. It deals with duplicate packets, lost packets, etc. It also is responsible for authentication through the 3 way handshake. SYN: The client sends a segment with the SYN (Synchronize Sequence Number) flag set to the server, indicating that it wants to start communication and specifying the sequence number it will use for its segments1.
SYN-ACK: The server responds to the client’s request with a segment that has both the SYN and ACK flags set. The ACK flag acknowledges the receipt of the client’s SYN segment, while the SYN flag indicates the sequence number that the server will use for its segments1.
ACK: The client sends a final segment with the ACK flag set to acknowledge the receipt of the server’s SYN-ACK segment. At this point, both the client and server have synchronized their sequence numbers and established a reliable connection, allowing them to begin transmitting data.

Protocol suite - a set of protocols designed to work together. TCP/IP For example.

![image](https://github.com/derekrjohnson/Network-Protocols/assets/142181223/30d776cb-117d-4c29-b39e-7cff6cfdbd2d)

TCP has responsibility to ensure a secure connection at the session layer with the 3 way handshake.



