---
{"dg-publish":true,"permalink":"/client-server-architecture/","dg-note-properties":{}}
---

## Server
- Server is just a process on a machine that serves something
- The machine that has this serving process is known as **Mainframe**
- Something like MySQL running on port 3306, is a server
- It provides the service of running the queries
## Client
- Client is a Just a Process that wants to avail the service of a Server
- Ex: Workbench is a Client, or even our JDBC programs are also a client
- It cannot execute the queries without a MySQL Server.
- **Client is Responsible to Initialize a connection**
## Channel
- A Channel is a medium, through which data travels
- It can be wired or wireless
- A Network Interface Card is used to connect to a Channel
- The NIC acts as an interface, between the host and the channel
- The NIC is connected to a socket
- A Channel can never be empty, it always keeps sending something, even useless
- Hence, header formats are required to identify if something useful is coming
## Socket
- A Socket is anything to which something can be connected like a Ethernet Socket, USB Socket
- A Socket is not a port
## Ports
- A Port no is a 2 byte (16 bit ) unsigned number (MAX: 65636)
- Ports 0 - 1023 are reserved for well know applications by IEEE
- Port is just a number socket
- It is only logical, Socket is actually present as a process
## Loopback Address
- Loopback address is a special address
- It is used when we want to send packets back to our machine itself
- It is also commonly referred to as a `localhost
- It sends a packet from the system back into the system