# Day-23 – WebRTC Notes

## What WebRTC Actually Is
WebRTC (Web Real-Time Communication) is a set of open standards that enables:
- Peer-to-peer
- Real-time
- Audio, video, and data transfer

Directly between browsers.
No plugins. No native apps.

---

## Core Idea
Unlike traditional client-server models:
- Data flows client ↔ client
- Servers are used only for signaling
- Media does NOT pass through backend

Result:
- Ultra-low latency
- Less server load
- More upfront complexity

---

## What WebRTC Is Good At
WebRTC shines when:
- Latency must be minimal
- Media is real-time
- Participants are limited

Use cases:
- Video conferencing
- Voice calls
- Screen sharing
- Online interviews
- Live collaboration tools
- Peer-to-peer file transfer

If milliseconds matter, WebRTC wins.

---

## What WebRTC Is NOT Good At
WebRTC struggles when:
- Massive audiences are involved
- Recording or broadcasting is required
- Central control is needed

For these:
- Use streaming protocols
- Use media servers (SFU / MCU)

WebRTC scales, but not casually.

---

## WebRTC Building Blocks

### 1. Media Capture
- Camera
- Microphone
- Screen
  Controlled via browser permissions.

### 2. Peer Connection
- Direct encrypted P2P connection
- Optimized for low latency and packet loss

### 3. Data Channels
- Send arbitrary data (files, messages, signals)
- Reliable or unreliable modes

---

## How WebRTC Works (Reality Version)

### Step 1: Signaling (You Build This)
Peers exchange:
- Connection info
- Media capabilities
- Network details

WebRTC does NOT define signaling.
You use:
- WebSocket
- HTTP
- Any messaging system

---

### Step 2: NAT Traversal
Most devices are behind routers.

WebRTC uses:
- STUN → discovers public IPs
- TURN → relays traffic when direct connection fails

TURN is reliable but expensive.

---

### STUN and TURN (In Short)

**STUN**
- Tells client its public IP and port
- Helps peers connect directly
- Lightweight, fast, cheap
- Fails with strict NATs or firewalls

**TURN**
- Acts as a relay server
- Media flows through TURN
- Reliable but expensive
- Higher latency and bandwidth cost

One-line summary:
- STUN: "Can we connect directly?"
- TURN: "Fine, route it through me."

WebRTC always tries STUN first, TURN only if necessary.

---

### Step 3: Secure Peer Connection
- DTLS for key exchange
- SRTP for media encryption
- Encryption is mandatory

No encryption. No WebRTC.

---

## WebRTC vs WebSocket (Quick Contrast)

- WebSocket:
    - Client-server model
    - Good for messages
    - Easier to scale

- WebRTC:
    - Peer-to-peer
    - Good for presence (audio/video)
    - Harder to scale

Different tools. Different jobs.

---

## Security by Default
WebRTC enforces:
- Encrypted connections
- Permission-based media access
- Browser-level sandboxing

Security is not optional. It’s built in.

---

## Core Insight
WebRTC removes the middleman from real-time communication.

If WebSocket is for messages,
WebRTC is for presence.