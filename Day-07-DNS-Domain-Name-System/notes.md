## DNS – Domain Name System

DNS is the internet’s phonebook.
Hum names yaad rakhte hain (google.com),
computers numbers samajhte hain (IP address).

DNS domain name ko IP address me convert karta hai.

---

## Layman Example
- Aap "google.com" type karte ho
- DNS bolta hai: iska address ye IP hai
- Browser us IP pe request bhejta hai

---

## DNS Resolution Steps (Behind the Scenes)

### Step 1: Browser Cache
Browser check karta hai:
“Is domain ka IP recently dekha tha kya?”
- Yes → direct use
- No → next step

---

### Step 2: OS Cache
Operating System apni DNS memory check karta hai.

---

### Step 3: DNS Resolver (ISP / 8.8.8.8)
Ye middleman hota hai.
Agar iske paas answer nahi hai,
to ye aage poochta hai.

---

### Step 4: Root DNS Server
Resolver poochta hai:
“Who knows about .com domains?”

Root bolta hai:
“Mujhe exact IP nahi pata, .com wale jaante hain.”

---

### Step 5: TLD Server (.com)
Resolver poochta hai:
“Who handles google.com?”

TLD reply karta hai:
“Ye authoritative servers handle karte hain.”

---

### Step 6: Authoritative DNS Server
Resolver poochta hai:
“What is the IP of www.google.com?”

Authoritative reply:
“142.250.72.14”

---

### Final
IP browser ko mil jata hai,
browser server se page load karta hai.

---

## Key Points
- DNS = Name → IP
- Root server IP nahi deta, direction deta hai
- Authoritative server final answer deta hai
- DNS caching speed improve karta hai