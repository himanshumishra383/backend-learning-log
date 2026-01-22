# Day-21 – WebSocket – Real-Time Communication

## What is WebSocket?
WebSocket is a protocol that enables **full-duplex, persistent communication**
between a client and a server over a **single TCP connection**.

Unlike HTTP (request–response), WebSocket keeps the connection open
and allows **instant two-way data flow**.

---

## Why WebSocket Exists
HTTP is:
- Request → Response
- Stateless
- Client-initiated only

Real-time systems need:
- Instant updates
- Server push
- Low latency

WebSocket solves this cleanly.

---

## Where WebSocket Shines
- Chat applications
- Live notifications
- Multiplayer games
- Stock & crypto price feeds
- Live dashboards
- Collaborative editors
- Real-time analytics

If polling feels wrong, WebSocket is the answer.

---

## WebSocket vs HTTP
| Feature | HTTP | WebSocket |
|------|------|----------|
| Connection | Short-lived | Persistent |
| Direction | Client → Server | Client ↔ Server |
| Latency | Higher | Low |
| Real-time | Simulated | Native |

---

## Security
- `ws://` → insecure
- `wss://` → WebSocket over TLS (secure)

✅ **Always use WSS in production. No exceptions.**

---

## The Bottom Line
HTTP asks questions.  
WebSocket keeps a conversation open.

If your system needs:
- Instant updates
- Two-way communication
- Low latency

WebSocket is the correct tool.