# Day-21 – WebSocket Notes

## What WebSocket Actually Is
WebSocket is a protocol that provides:
- Full-duplex communication
- Persistent connection
- Single TCP connection
- Client and server can send data anytime

No repeated requests. No waiting turns.

---

## How WebSocket Works

### Step 1: HTTP Handshake
WebSocket starts as HTTP.

Client sends:
GET /ws HTTP/1.1  
Upgrade: websocket  
Connection: Upgrade

Server responds:
HTTP/1.1 101 Switching Protocols

After this:
- HTTP is gone
- WebSocket takes over

---

### Step 2: Persistent Connection
- One TCP connection
- Stays open
- Bi-directional data flow
- No headers per message
- Minimal overhead

---

## Why HTTP Fails at Real-Time
HTTP is:
- Stateless
- Client-initiated
- Request → Response

To fake real-time, developers used:
- Polling
- Long polling
- Repeated fetch calls

Problems:
- Inefficient
- High latency
- Server-wasteful

WebSocket removes the hack.

---

## WebSocket + TLS = WSS
Just like:
- HTTP → HTTPS
- WebSocket → WSS

WSS = WebSocket over TLS  
Encrypted + trusted communication.

---

## What WebSocket Is NOT
- ❌ Not a replacement for REST
- ❌ Not ideal for request-response APIs
- ❌ Not stateless
- ❌ Not cheap to scale blindly

Persistent connections cost memory and planning.

---

## Scaling WebSocket (Reality Check)
Scaling requires:
- Connection management
- Sticky sessions or shared state
- Message brokers (Redis, Kafka, Pub/Sub)
- Backpressure handling

Powerful, but not free.

---

## WebSocket vs Alternatives
- SSE → One-way, simpler
- HTTP polling → Easy, inefficient
- WebSocket → Real-time, two-way, complex

Choose based on problem, not hype.

---

## Core Insight
WebSocket is not “faster HTTP”.

It is **continuous communication**.

Use it intentionally.  
Design it carefully.  
Scale it responsibly.