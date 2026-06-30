---
{"dg-publish":true,"permalink":"/common-classes/","dg-note-properties":{}}
---

## `InetAddress`
- This is a class used to represent an IP Address
- It can be used to represent both IPv4 and IPv6 addresses
- All constructors and uses **Factory Methods**
#### Methods
1. `static getAllByName(String host)`: Returns all the IP addresses of the given host name
## `ServerSocket`
- Used to create a server
- It takes a port number in the constructor and throws `IOException` if port is busy 
- `accept` method puts it in an infinite loop until a client connects
## `Socket`
- It is used at the client side
- Used for TCP
- It will initialize connection with the server
- It has `getInputStream` and Output Stream methods for communication
## `DatagramSocket`
- Used to open UDP on a particular port
- it has `receive(DatagramPacket pack)` to receive, blocking method
- `send(DatagramPacket pack)`
- This class is used to create socket at both sides, this asks for a optional port in the constructor
## `DatagramPacket`
 - Used for UDP
 - A Datagram is a Self Contained Packet
 - It is generally used for Peer-to-Peer, but still used with [[Client Server Architecture\|Client Server Architecture]]
 - It is a byte[] since, a byte can be converted to any format
 - It contains port, data, length of data, Ip address (`InetAddress`) of the destination
 - Packet has methods to retrieve all of the above from the packet, on the receiving end it will return the port , address, etc. of the sender