## Evolution of System Architectures

### 1. Standalone / Monolithic Systems (Pre-network era)
- One machine did everything:
    - Input
    - Processing
    - Storage
    - Output
- No network, no client, no server
- Entire app ran as one process

Why it worked:
- Hardware was expensive
- Networking was slow or unavailable
- Users worked close to machines

Why it failed:
- One machine = one user
- No data sharing
- Scaling = buy a bigger machine
- Vertical scaling hits a hard limit

---

### 2. Mainframe + Dumb Terminals
- Central mainframe handled:
    - All computation
    - All data
- Terminals had:
    - Keyboard + screen
    - Zero logic

Why it was revolutionary:
- Multiple users on one system
- Single source of truth
- Centralized maintenance

Cost:
- Mainframes were extremely expensive
- Single point of failure
- If mainframe died → everyone stopped

This was centralized computing at scale.

---

### 3. File Server Architecture
- Central server stored files (data)
- Clients ran application logic locally
- Clients read/write shared files over network

Why it felt like progress:
- PCs became powerful
- Better user interfaces
- Servers cheaper than mainframes

Why it failed:
- Large data transferred over network
- Data corruption (multiple users editing same file)
- Business logic duplicated on clients
- Weak security

Core lesson:
Moving raw data is expensive and dangerous.

---

### 4. Early Distributed Systems (Peer-to-Peer-ish)
- No central server
- Each node acted as client + server
- Data and logic spread across machines

Appeared in:
- Early collaboration tools
- Research systems
- Multiplayer games

Problems:
- Synchronization is hard
- Failure handling is brutal
- Debugging becomes archaeology

Key truth discovered:
Distributed systems fail in ways centralized systems never imagine.

---

## Big Takeaway
Earlier systems were not bad designs.
They were perfect solutions for their time.

Client–server architecture emerged because it:
- Balanced central control
- With distributed access
- Allowed horizontal scaling

Modern systems still negotiate the same trade-offs,
just with better tools and more RAM.