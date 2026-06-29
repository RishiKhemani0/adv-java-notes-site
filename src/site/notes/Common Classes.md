---
{"dg-publish":true,"permalink":"/common-classes/","dg-note-properties":{}}
---

## `INetAddress`
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
- It will initialize connection with the server
- It has `getInputStream` and Output Stream methods for communication
