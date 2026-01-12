## Need for Client–Server Architecture

Client–server didn’t appear for fashion.
It appeared because earlier systems collapsed under scale, distance, and coordination.

---

### Core Problems in Early Systems

#### 1. Shared data became unavoidable
- Multiple users needed the same data
- File-based and local systems started lying
- Two machines editing same data = corruption
- Centralizing data access became mandatory

#### 2. Users were no longer in the same room
- Standalone and terminal systems assumed proximity
- Internet spread users across cities and continents
- Systems had to work over unreliable networks

#### 3. Scaling users ≠ scaling machines
- Vertical scaling hit cost and hardware limits
- File servers drowned in network traffic
- Systems needed horizontal scaling

#### 4. Logic duplication killed consistency
- Business rules on every client caused divergence
- Updating logic meant updating all clients
- Bugs multiplied silently

---

## The Key Insight
- Ship requests, not raw data
- Enforce rules once, centrally
- Verify centrally, don’t trust clients

This shift made large-scale software possible.

---

## What Is Client–Server?

A role-based separation, not a hardware rule.

### Client
- Initiates requests
- Handles user interaction
- Presents data

### Server
- Listens for requests
- Validates (auth, authz, sanity)
- Executes business logic
- Manages shared resources
- Returns response

Client asks. Server decides.
Client borrows data. Server owns trust.

---

## Interaction Flow
1. Client sends request
2. Server validates request
3. Server executes business logic
4. Server interacts with storage/services
5. Server sends response (data/status/error)

Nothing happens without a request.
Nothing is trusted without verification.

---

## Why This Model Scales (When Done Right)

- Single source of truth
- Centralized control, distributed access
- Loose coupling

Benefits:
- Clients can change UI independently
- Servers can optimize internals safely
- Multiple clients (web, mobile, IoT) reuse same server

---

## What Client–Server Is NOT
- Not just frontend–backend buzzword
- Not automatically scalable or secure
- Not always two machines

Examples:
- Browser →