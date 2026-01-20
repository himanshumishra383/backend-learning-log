# HTTP vs HTTPS: What Actually Happens When You Open a Website

Every time you type a URL and hit Enter,
a quiet negotiation happens between your browser and a server.

The rules of that negotiation are defined by HTTP and HTTPS.

---

## 1. What is HTTP?
HTTP (HyperText Transfer Protocol) is the foundation of the web.
It defines how clients (browsers) and servers communicate.

Core characteristics:
- Stateless: each request is independent
- Application-layer protocol
- Plain text communication

How HTTP works (simplified):
1. Browser sends a request (GET, POST, PUT, DELETE)
2. Server processes it
3. Server sends a response (status code + data)

Example:
GET /products HTTP/1.1
Host: example.com

---

## 2. The Big Problem with HTTP
Everything sent over HTTP is:
- Visible
- Modifiable
- Interceptable

If you submit a password over HTTP,
anyone on the network can read it.
No hacking required. Just listening.

---

## 3. What is HTTPS?
HTTPS (HyperText Transfer Protocol Secure)
is HTTP wrapped inside encryption.

Technically:
HTTPS = HTTP + TLS (Transport Layer Security)

The rules of HTTP stay the same.
Only the data transport changes.

---

## 4. What HTTPS Actually Fixes
HTTPS provides three guarantees:

### 1. Encryption (Confidentiality)
- Data is encrypted before transmission
- Attackers see gibberish

### 2. Integrity
- Data cannot be altered in transit
- Tampering breaks the connection

### 3. Authentication
- You know you’re talking to the real server
- Prevents fake websites and MITM attacks

---

## 5. How HTTPS Works (TLS Handshake)
Simplified but accurate flow:

1. Client Hello
2. Server Hello
3. Certificate Verification
4. Key Exchange
5. Secure communication begins

After this, HTTP behaves normally —
just invisibly encrypted.

---

## 6. SSL vs TLS (Short Truth)
- SSL is obsolete
- TLS is what’s actually used
- People still say “SSL certificate” out of habit

Correct term: TLS certificate

---

## 7. HTTP vs HTTPS: Direct Comparison

HTTP:
- No encryption
- Plain text
- No authentication
- Marked “Not Secure”