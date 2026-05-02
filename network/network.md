# These are network notes
## Network
- A network is when two or more device exchange data.
Here's a general overview of what happens when you open a website:
Your PC ---> router ---> provider ---> backbone network operator ---> data center ---> website
## OSI model
The OSi model is an abstract network model of open system interaction; in simple terms, 
it is an ideal model that helps specialists determine at which stage a network error occurred.
It have a 7 layer:
- L1 - Physical layer. This is a hardware layer. Her, data is transmitted form of electrical signals, light pulses, or radio waves.
- L2 - Link layer. Enables data transmission between two devices on the same local area network. Mak addresses are used here.
- L3 - Network layer. Is responsible for routing data between different networks. The IP address is already here.
- L4 - Transport layer. This layer is responsible for ensuring data transmission between two applications. It does this through that the programs use.
- L5 - Session layer. It ensures synchronization between devices, manages dialogs and terminates sessions.
- L6 - Presentation layer. It decodes, encodes, compresses and encrypts files.
- L7 - Applycation layer. Provides network services directly to HTTP, FTP, DNS.  

## TCP/IP model
TCP/IP is the core set of network protocols upon which the modern Internet is built. It is similar the OSI model but has only 4 layers instead of 7. 
Layers 1 and 2 in the OSI model correspond to Layer 1 in TCP/IP, and Layers 5, 6, and 7 correspond to Layer 4.
- L1 - Network access. It combines L1 and L2 in OSI model.
- L2 - Internet. L3 for OSI model.
- L3 - Transport. L4 for OSI model.
- L4 - Application. It combines L5, L6 and L7 in OSI model

## Firewall
A firewall is a network traffic filter that determinate which packets to allow through and which to block. Protection against unauthorized access - close all ports
except a necessary ones. For example, onep only ports 22(SSH), 80(HTTP) and 443(HTTPS), and block all others.
Types of firewalls:
- Network firewall - sits at the edge of the entire network. It filters traffic for all devices at once. For example, AWS Security Groups are network firewalls.
- Stateless — checks each packet individually against rules. Simple but dumb — does not understand the context of the connection.
- Stateful (SPI) — tracks the state of connections. Understands that this packet is a response to an already established connection. Smarter and more secure.
- WAF (Web Application Firewall) — specifically for web applications. Protects against SQL injections, XSS attacks, and DDoS. For example, CloudFlare and AWS WAF.
## VPN
 
### SSH
SSH (Secure Shell) is a protocol for securely connecting to a remote server over a network.
### Load Balancer
A load balancer distributes incoming traffic among multiple servers.

