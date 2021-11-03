# NETWORKING ROOM. 

## OSI 

> OSI model stands for OPEN SYSTEM INTERCONNECTION model. It consists of 7 layers namely: 

1. Application Layer.   - `A`nytime
1. Presentation Layer.  - `P`assword
1. Session Layer.       - `S`ecret
1. Transport Layer.     - `T`ell
1. Network Layer.       - `N`ot
1. Data Link Layer.     - `D`o
1. Physical Link Layer. - `P`lease

### Functions of each layer in one sentence. 

1. Application Layer.   - It provides networking options to programs.  
1. Presentation Layer.  - Translates the data into standardised format and handles encryption as well as compression for the correct transformation of the data.
1. Session Layer.       - It responsible for creating and maintaining sessions this sessions are usually remote sessions so they are containerized as well so the data between the sessions dont get mixed up. 
1. Transport Layer.     - Here is where the transmission protocol gets decided i.e UDP OR TCP as soon as the protocols are decided the data gets divided into smaller bite-sized pieces which are known as segments in TCP and Datagrams in UDP. 
1. Network Layer.       - It is responsible for find ing the destination your request. 
1. Data Link Layer.     - It adds the MAC address to packets of the receiving endpoint and checks if the data has been corrupted or not. 
1. Physical Link Layer. - It's converts the binary data into signals.

# ENCAPSULATION AND DE-ENCAPSULATION OF DATA
# TCP/IP 

> TCP stands for Tranmission controlled protocol and is a connection-based protocol meaning first a stable connection is made between the 2 computers and that process is known as Three way handshake. 

It consist of 4 layers namely,

1. Application Layer. 
1. Transport Layer. 
1. Internet Layer. 
1. Network Interface Layer. 

## THREE WAY HANDSHAKE. 

> When you attempt to make a connection, your computer first sends a special request to the remote server indicating that it wants to initialise a connection. This request contains something called a SYN (short for synchronise) bit, which essentially makes first contact in starting the connection process. The server will then respond with a packet containing the SYN bit, as well as another "acknowledgement" bit, called ACK. Finally, your computer will send a packet that contains the ACK bit by itself, confirming that the connection has been setup successfully. With the three-way handshake successfully completed, data can be reliably transmitted between the two computers. Any data that is lost or corrupted on transmission is re-sent, thus leading to a connection which appears to be lossless. 

### ICMP PROTOCOL
> Ping works using the ICMP protocol, which is one of the slightly less well-known TCP/IP protocols that were mentioned earlier. The ICMP protocol works on the Network layer of the OSI Model, and thus the Internet layer of the TCP/IP model

## Ping 

ping -v -> verbose
ping -i -> interval
ping -4 -> defaults to IPv4. 
ping -6 -> defaults to IPv6. 

## Traceroute
> The internet is made up of many, many different servers and end-points, all networked up to each other. This means that, in order to get to the content you actually want, you first need to go through a bunch of other servers. Traceroute allows you to see each of these connections -- it allows you to see every intermediate step between your computer and the resource that you requested. The basic syntax for traceroute on Linux is this: traceroute <destination>

By default, the Windows traceroute utility (tracert) operates using the same ICMP protocol that ping utilises, and the Unix equivalent operates over UDP. This can be altered with switches in both instances.

## WHOIS 

> Helps to find the information about the server owner. 
whois google.com

## dig

> Dig allows us to manually query recursive DNS servers of our choice for information about domains
dig <domain> @<dns-server-ip>
dig google.com @1.1.1.1


### MISC.
DNS STANDS FOR DOMAIN NAME SYSTEM.
