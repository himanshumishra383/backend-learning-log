# IP: TCP/IP, UDP & 3-Way Handshake

TCP/IP is often spoken as one thing.
It isn’t.

It’s a family of protocols stacked like a well-behaved bureaucracy,
where each layer refuses to do more than its job.

---

## TCP/IP Stack (Mental Model)
- IP: Moves packets between addresses
- TCP / UDP: Decide behavior (reliability vs speed)
- Application protocols: Meaning (HTTP, DNS, SMTP)

Each layer is intentionally limited.
Fewer promises → fewer failures.

---

## Internet Protocol (IP) Recap
IP is brutally minimal.

It:
- Assigns IP addresses
- Breaks data into packets
- Routes packets across networks

IP guarantees nothing:
- No delivery guarantee
- No ordering guarantee
- No duplication protection

This is not laziness.
This is what makes IP fast, simple, and universal.

---

## TCP: Reliability as a Feature
TCP exists because most applications prefer correctness over speed.

TCP guarantees:
- Data arrives
- Data arrives in order
- Lost data is retransmitted
- Congestion is handled gracefully

To do this, TCP keeps state:
- Sequence numbers
- Acknowledgements
- Retransmission timers
- Flow & congestion control

State is expensive.
But it buys safety.

### TCP is used when:
- HTTP / HTTPS
- APIs
- Databases
- File transfers
- Authentication systems

If losing data breaks meaning, TCP is non-negotiable.

---

## UDP: Speed Over Certainty
UDP is TCP’s impatient sibling.

UDP provides:
- No connection setup
- No delivery guarantees
- No ordering
- No retransmissions

It sends packets and hopes for the best.

Why choose this?
Because sometimes:
- Late data is worse than missing data
- Overhead kills performance
- The application can handle loss better than the network

### UDP powers:
- Video streaming
- Online gaming
- VoIP
- DNS queries

UDP trades correctness for timeliness.
Architects choose it deliberately.

---

## TCP vs UDP: The Real Difference
The difference is NOT:
Reliable vs unreliable.

The real difference is:
**Who handles failure.**

- TCP handles failure inside the protocol
- UDP pushes failure handling to the application

UDP isn’t reckless.
It’s honest.

---

## TCP Three-Way Handshake
Before TCP sends real data, it performs a ritual.
This ritual creates shared state between two machines that have never met.

This is the famous 3-way handshake.

---

### Step 1: SYN – “Can we talk?”
Client sends SYN.

This packet says:
- I want to establish a connection
- Here is my initial sequence number

No data yet.
Just intent.

The client commits resources and waits.
This is a risk.

---

### Step 2: SYN-ACK – “I’m listening”
Server replies with SYN + ACK.

This says:
- I received your SYN
- Here is my initial sequence number
- I’m willing to talk

Now both sides know:
- Each other’s sequence numbers
- Packets can travel both ways

The server allocates resources here.
This is why SYN floods are dangerous.

---

### Step 3: ACK – “Connection established”
Client sends final ACK.

This says:
- I received your SYN-ACK
- We are synchronized

At this point:
- Connection is officially open
- Data transfer can begin

No application data was exchanged.
This was purely about trust and synchronization.

---

## Why Three Steps? Why Not Two?
Because networks lie.

Packets can:
- Be duplicated
- Be delayed
- Arrive out of order

The third ACK ensures:
- Both sides are reachable
- Both sides agree on state
- Old or duplicate packets don’t create ghost connections

Two steps are not enough to eliminate ambiguity.
The third ACK closes the loop.

---

## Why This Matters Architecturally
The TCP handshake explains:
- Why TCP is slower than UDP
- Why cold starts feel expensive
- Why connection reuse matters
- Why connection limits exist
- Why SYN floods can cripple servers

Understanding SYN, SYN-ACK, ACK
is understanding the **cost of reliability**.

---

## Core Insight
TCP creates the illusion of a reliable pipe
on top of an unreliable network.

UDP refuses to lie and exposes reality.

Every modern system is a negotiation
between these two philosophies.