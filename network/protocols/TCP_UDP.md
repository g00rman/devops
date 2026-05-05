# TCP vs UDP
What is it
TCP and UDP are L4 (Transport layer) protocols. Responsible for delivering data between two devices.
TCP (Transmission Control Protocol)
Reliable protocol with guaranteed delivery.
3-way handshake (connection establishment):
```
Client → SYN      → Server
Client ← SYN-ACK ← Server
Client → ACK      → Server
```
Connection termination:
```
Client → FIN → Server
Client ← ACK ← Server
Client ← FIN ← Server
Client → ACK → Server
```
Characteristics:

- Guaranteed delivery — if a packet is lost, it retransmits
- Guaranteed order — packets arrive in the same order they were sent
- Flow control — does not overwhelm the receiver
- Congestion control — adapts to network conditions

Connection states:
```
LISTEN      — server waiting for connection
SYN_SENT    — client sent SYN
ESTABLISHED — connection established
TIME_WAIT   — connection closing
CLOSE_WAIT  — received FIN from remote
```
Used for: HTTP, HTTPS, SSH, SMTP, databases

# UDP (User Datagram Protocol)
Fast protocol with no delivery guarantee.
Characteristics:

- No handshake
- No delivery acknowledgment
- No packet order guarantee
- Less overhead → faster

Used for: DNS, VoIP, video streaming, online games, WireGuard VPN

