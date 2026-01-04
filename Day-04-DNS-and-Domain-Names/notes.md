## DNS & Domain Names

### What is DNS?
DNS (Domain Name System) is the internet’s phonebook.
It converts human-readable domain names into IP addresses.

Example:
- You type: google.com
- DNS finds the IP: 142.250.x.x
- Browser connects to that IP

Without DNS, we would have to remember IP addresses.

---

### Layman Example
- Domain name = Contact name (Mom)
- IP address = Phone number
  DNS works like your contacts app.

---

### Why DNS is Needed
- Humans remember names, not numbers
- Servers communicate using IPs
- DNS bridges the gap

---

### DNS Resolution Flow
1. Browser checks cache
2. OS checks local cache
3. Request goes to ISP DNS
4. Root DNS → TLD DNS → Authoritative DNS
5. IP address returned
6. Browser connects to server

---

### Domain Name Structure
Example: www.api.google.com

- Root: .
- TLD: .com
- Domain: google
- Subdomain: api / www

---

### Common DNS Record Types
- A: Domain → IPv4 address
- AAAA: Domain → IPv6 address
- CNAME: Alias to another domain
- MX: Mail server record
- NS: Name server info
- TXT: Verification / security info

---

### Public DNS Providers
- Google: 8.8.8.8
- Cloudflare: 1.1.1.1
-