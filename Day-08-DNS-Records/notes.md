## DNS Records

DNS records are instructions stored in DNS.
Each record answers a specific question about a domain.

Think of DNS like a notice board:
Different slips = different jobs.

---

## A Record (Address)
Question:
“What is the IPv4 address of this domain?”

- Maps domain → IPv4
- Most basic & important record

Example:
example.com → 93.184.216.34

If A record breaks → website disappears.

---

## AAAA Record (IPv6)
Same as A record, but for IPv6.

Example:
example.com →
2606:2800:220:1:248:1893:25c8:1946

Exists because IPv4 addresses ran out.

---

## CNAME Record (Alias)
Question:
“Is this domain a nickname for another domain?”

- Points domain → another domain (not IP)
- Used for subdomains

Example:
www.example.com → example.com

Rule:
CNAME = alias, not destination.

---

## MX Record (Mail Exchange)
Question:
“Where should emails for this domain go?”

- Used only for email delivery
- Has priority (lower number = higher priority)

Example:
example.com → mail.google.com (priority 10)

If MX is wrong:
- Website works
- Emails disappear (silent failure)

---

## TXT Record (Text / Verification)
Question:
“Can you prove something about this domain?”

Used for:
- Domain ownership verification
- Email security (SPF, DKIM, DMARC)
- Third-party services (Google, GitHub)

Example:
"v=spf1 include:_spf.google.com ~all"

TXT controls inbox vs spam.

---

## NS Record (Name Server)
Question:
“Who is authoritative for this domain?”

- Points to DNS servers responsible for the domain

Example:
example.com → ns1.cloudflare.com

Meaning:
“Trust these servers for answers.”

Wrong NS = entire domain goes dark.

---

## PTR Record (Reverse Lookup)
Question:
“What domain belongs to this IP?”

- IP → domain (reverse of A record)
- Used in email validation

Example:
93.184.216.34 → example.com

Mail servers care. Spammers hate it.

---

## SRV Record (Service Record)
Question:
“Where is a specific service running?”

- Defines service + protocol + port

Example:
_service._tcp.example.com →
server.example.com:5060

Used in:
- VoIP
- Chat systems
- Microservices discovery

---

## SOA Record (Start of Authority)
Question:
“Who owns this zone and how should it behave?”

Contains:
- Primary DNS server
- Admin email
- Refresh / retry rules

Rule:
Every DNS zone has exactly ONE SOA.

SOA = legal document of the domain.

---

## Conclusion
DNS looks simple, but it silently holds the internet together.
Understanding records makes debugging web issues easy.