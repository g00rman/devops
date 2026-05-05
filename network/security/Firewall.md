## Firewall
A firewall is a network traffic filter that determinate which packets to allow through and which to block. Protection against unauthorized access - close all ports
except a necessary ones. For example, onep only ports 22(SSH), 80(HTTP) and 443(HTTPS), and block all others.
Types of firewalls:
- Network firewall - sits at the edge of the entire network. It filters traffic for all devices at once. For example, AWS Security Groups are network firewalls.
- Stateless — checks each packet individually against rules. Simple but dumb — does not understand the context of the connection.
- Stateful (SPI) — tracks the state of connections. Understands that this packet is a response to an already established connection. Smarter and more secure.
- WAF (Web Application Firewall) — specifically for web applications. Protects against SQL injections, XSS attacks, and DDoS. For example, CloudFlare and AWS WAF.
