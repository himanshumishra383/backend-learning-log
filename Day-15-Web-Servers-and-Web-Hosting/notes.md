# Web Servers and Web Hosting

People often use “web server” and “web hosting” interchangeably.
That’s wrong.

Confusing them is like confusing an **engine** with a **garage**.

One runs the machine.
The other decides where the machine lives.

---

## What Is a Web Server?
A web server is software whose job is brutally simple:

- Listen for HTTP requests
- Decide what to do with them
- Send back HTTP responses

Examples:
- Apache
- Nginx
- Caddy
- IIS

They are **not websites**.
They are traffic cops for HTTP.

---

## What a Web Server Actually Does
At a practical level, a web server:
- Binds to a port (80 / 443)
- Accepts incoming connections
- Parses HTTP requests
- Serves static files OR forwards requests
- Handles concurrency, timeouts, reuse

Crucially:
A web server does **not** contain business logic.

It doesn’t know what a “user” is.
It doesn’t know what “checkout” means.
It only knows how to move bytes safely and efficiently.

---

## Static vs Dynamic Responsibility

Web servers usually play one or both roles:

### 1. Static Content Serving
- HTML, CSS, JS, images, videos
- Fast, cacheable, predictable

### 2. Request Forwarding (Reverse Proxy)
Dynamic requests are forwarded to:
- Application servers
- Backend frameworks
- Microservices

This separation exists because:
- Static files are cheap to serve
- Application logic is expensive and fragile
- Mixing them causes performance and security issues

That’s why production systems rarely expose app servers directly.

---

## What Is Web Hosting?
Web hosting answers a different question:

**Where does your server run?**

Hosting is infrastructure + operational responsibility.

It includes:
- Physical or virtual machines
- Network connectivity
- IP addresses
- Power, cooling, uptime
- Backups, firewalls, monitoring

A hosting provider gives your system a **place on the internet**.

Without hosting, a web server is just software on your laptop,
shouting into the void.

---

## Types of Web Hosting (Architectural View)

### Shared Hosting
- Multiple users share one server
- Cheap, limited
- Fine for blogs
- Terrible for control

### VPS (Virtual Private Server)
- Virtualized machine with guaranteed resources
- Full control over OS and server stack
- Where real backend learning starts

### Dedicated Hosting
- One physical machine, one customer
- Expensive, predictable
- Rarely needed today

### Cloud Hosting
- Infrastructure exposed via APIs
- Servers are disposable
- Auto-scaling is normal
- Failure is assumed

Cloud won because machines are treated as **cattle, not pets**.

---

## How Web Servers Fit into Hosting
A real-world stack looks like this:

- Cloud provider gives VM or container
- OS runs on that machine
- Web server runs on the OS
- Application runs behind the web server
- Database runs elsewhere
- Load balancer sits in front

Web server = front door  
Hosting = building

You can change one without rewriting the other.

---

## Why Web Servers Exist at All
Fair question:
“Why not let the app handle HTTP directly?”

Because web servers are:
- Faster at I/O
- Better at handling thousands of connections
- Safer to expose publicly
- Optimized for caching and compression
- Hardened against malformed traffic

They absorb chaos so your application doesn’t have to.