## Routers

### What is a Router?
A router is a network device that connects multiple networks and forwards data packets
between them based on destination IP addresses.

It works like a traffic controller for internet data.

---

### Where Router Works (OSI Model)
- Operates at Layer 3 (Network Layer)
- Uses IP addresses for decision making

---

### Layman Example
- You send a letter
- Post office checks address
- Chooses best route
- Delivers step by step

Router does the same for data packets.

---

### Key Functions
- Connects Networks: LAN to WAN (home Wi-Fi → internet)
- Forwards Data: Sends packets to correct destination
- Shares Internet: Multiple devices use one connection
- Manages Traffic: Uses routing tables
- Provides Security: Firewall, NAT, filtering

---

### How Router Works (Step-by-Step)
1. Packet Creation  
   Data is broken into packets

2. Destination Check  
   Router reads destination IP from packet header

3. Path Finding  
   Routing table is checked to find best next hop

4. Forwarding  
   Packet is sent to next router until destination

---

### Types of Routers
- Access Router  
  Home / office Wi-Fi routers

- Edge Router  
  Connects ISP network to other networks

- Core Router  
  High-speed backbone routers of internet

---

### Router vs Switch
- Router: Uses IP, connects networks
- Switch: Uses MAC, connects devices in same network

---

### Router & Backend
- Every API request passes through routers
- Load balancers are advanced routers
- Network latency often router-dependent