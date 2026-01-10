## Full DNS Query Flow (Browser Perspective)

### 1. Browser starts with a name
- Browser understands domain names
- Network works only with IP addresses
- Goal: convert domain → IP (DNS resolution)

---

### 2. Browser DNS Cache
- Browser checks its own DNS cache
- If record exists and TTL not expired → IP found
- No DNS query needed

---

### 3. Operating System Cache
- Browser asks OS:
  "Do you already know this IP?"
- OS maintains shared DNS cache
- If not found → next layer

---

### 4. DNS Resolver (ISP / Public DNS)
- OS forwards request to DNS resolver
- Browser waits, resolver does the work
- Resolver performs recursive lookup

---

### 5. Root DNS Servers
- Resolver asks:
  "Who handles .com?"
- Root servers don’t know IPs
- They return TLD servers

---

### 6. TLD Servers (.com)
- Resolver asks:
  "Who manages example.com?"
- TLD replies with authoritative name servers
- This is delegation, not resolution

---

### 7. Authoritative DNS Server
- Resolver asks:
  "What is the IP of example.com?"
- Authoritative server owns the truth
- Responds with:
    - A record (IP)
    - TTL

---

### 8. Resolver Caches the Answer
- Stores IP in cache
- Honors TTL
- Reduces global DNS load

---

### 9. Browser Gets the IP
- IP flows back:
  Authoritative → Resolver → OS → Browser
- DNS work is done

---

### 10. Actual Website Loading Begins
Only after DNS resolution:
1. TCP / QUIC handshake
2. TLS handshake (HTTPS)
3. HTTP request
4. Server sends HTML
5. Browser renders UI

DNS is the entry gate.

---

## Key Notes
- Resolver = recursive
- DNS servers = iterative
- Caching makes DNS fast
- TTL controls freshness vs speed

✔ Completed