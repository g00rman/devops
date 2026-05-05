# Proxy
What is it
An intermediary server that sits between the client and the destination server.

## Forward Proxy
Sits in front of clients. Forwards client requests to the internet.
`Client → Forward Proxy → Internet → Server`
Use cases:

- Hide client IP
- Bypass geo-restrictions or corporate blocks
- Cache responses for multiple clients
- Filter outgoing traffic (corporate networks)


## Reverse Proxy
Sits in front of servers. Accepts requests from the internet and forwards to backend.
`Internet → Reverse Proxy → Backend servers`

Use cases:

- Hide backend server IPs
- SSL termination
- Load balancing
- Caching static content
- Rate limiting

nginx as reverse proxy:
```
server {
    listen 80;
    server_name example.com;

    location / {
        proxy_pass http://localhost:3000;
        proxy_set_header Host $host;
        proxy_set_header X-Real-IP $remote_addr;
    }
}
```
How layers relate to proxy
```
Forward proxy  — L7 (understands HTTP, can filter by URL)
Reverse proxy  — L7 (understands HTTP, routes by path)
SOCKS proxy    — L4 (works with any TCP/UDP traffic)
```
How everythink connect
```
User
  ↓ HTTPS (L7)
  ↓ TLS handshake
  ↓ TCP connection (L4) — 3-way handshake
  ↓ IP routing (L3)
  ↓
Reverse Proxy (nginx)
  ↓ SSL termination
  ↓ HTTP (L7) forwarded to backend
  ↓
Load Balancer
  ↓ distributes across servers
  ↓
[S1] [S2] [S3]
  ↓
Database
```
