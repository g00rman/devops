# DNS
What is it
DNS (Domain Name System) — system that resolves domain names to IP addresses. Works at L7, uses UDP port 53 (TCP for large responses).
Record types:
```
A     — domain → IPv4 address
        example.com → 93.184.216.34

AAAA  — domain → IPv6 address

CNAME — alias to another domain
        www.example.com → example.com

MX    — mail server for domain
        example.com → mail.example.com

TXT   — text record (SPF, DKIM, verification)

NS    — nameserver for domain

PTR   — reverse DNS (IP → domain)

SOA   — zone information
```
Resolution process
```
1. Browser checks local cache
2. Query to OS resolver (/etc/hosts)
3. Query to recursive resolver (e.g. 8.8.8.8)
4. Recursive resolver queries root nameserver
5. Root → TLD nameserver (.com)
6. TLD → authoritative nameserver (example.com)
7. Authoritative returns IP
8. Recursive resolver caches and returns to client
```
## TTL
Time To Live — how long a record is cached.
If TTL=3600 the record is cached for 1 hour.
Migration tip: before changing server IP — lower TTL to 60, change IP, after successful migration restore TTL.

