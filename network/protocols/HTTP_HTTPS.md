# HTTP / HTTPS
What is it
HTTP (HyperText Transfer Protocol) — L7 (Application layer) protocol for transferring data on the web. HTTPS = HTTP + TLS encryption.
HTTP methods:
```
GET     — retrieve a resource
POST    — create a resource
PUT     — replace a resource entirely
PATCH   — partially update a resource
DELETE  — delete a resource
HEAD    — like GET but without body (headers only)
OPTIONS — what methods are supported
```
Status codes:
```
2xx — success
  200 OK
  201 Created
  204 No Content

3xx — redirect
  301 Moved Permanently
  302 Found (temporary)
  304 Not Modified (from cache)

4xx — client error
  400 Bad Request
  401 Unauthorized (not authenticated)
  403 Forbidden (no permission)
  404 Not Found
  429 Too Many Requests

5xx — server error
  500 Internal Server Error
  502 Bad Gateway (nginx got no response from backend)
  503 Service Unavailable
  504 Gateway Timeout
```
HTTP headers:
```
### Request headers
Host: example.com
Authorization: Bearer token123
Content-Type: application/json
User-Agent: Mozilla/5.0
Accept: application/json

### Response headers
Content-Type: application/json
Cache-Control: max-age=3600
Set-Cookie: session=abc123
X-RateLimit-Remaining: 99
```
# HTTP + TLS = HTTPS
TLS handshake happens before any data is transferred:
```
1. Client Hello — TLS version, supported cipher suites
2. Server Hello — chosen version, certificate
3. Client verifies certificate via Certificate Authority
4. Key exchange (Diffie-Hellman)
5. Encrypted connection established
```
SSL Termination — nginx decrypts HTTPS and forwards to backend over HTTP:
`Client → HTTPS → nginx → HTTP → App server`
HTTP versions:
```
HTTP/1.1 — one connection, one request at a time
HTTP/2   — multiplexing, multiple requests in one connection
HTTP/3   — over UDP (QUIC), faster handshake
```
