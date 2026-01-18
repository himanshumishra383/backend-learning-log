# IP: Data Segmentation, Error Checking & Retransmission

If the internet were perfect, none of this would exist.
But the internet is hostile, lossy, and unpredictable.

TCP exists to survive failure, not eliminate it.

---

## Data Segmentation: Breaking the Message to Save the Message
Sending large data as one piece is a terrible idea.

Networks have limits:
- Maximum Transmission Unit (MTU)
- Router buffer sizes
- Varying link capacities

So instead of sending a “file”,
TCP breaks it into **segments**.

This happens at the transport layer.

Each segment:
- Carries a slice of data
- Has a sequence number
- Can travel independently

Why this matters:
- Smaller chunks reduce loss cost
- Routers forward packets efficiently
- Different paths can be used
- If one segment is lost, only that segment is retransmitted

Segmentation is how large data survives small pipes.

---

## Sequence Numbers: The Hidden Glue
Once data is segmented, order is no longer guaranteed.

Segments may:
- Arrive late
- Arrive early
- Arrive twice
- Arrive out of order

TCP assigns **sequence numbers** so the receiver can:
- Reassemble data correctly
- Detect missing segments
- Discard duplicates

Without sequence numbers,
segmentation would create scrambled noise.

---

## Error Checking: Trust, but Verify
Networks flip bits.
Memory glitches.
Packets get corrupted.

TCP never assumes correctness.
It checks.

Each TCP segment includes a **checksum**:
- Calculated over header + data
- Verified on receipt

If the checksum fails:
- Segment is silently discarded
- No acknowledgement is sent

This silence is intentional.
Corrupted data must never propagate.

Error checking ensures:
- Corruption is detected early
- Bad data doesn’t poison application logic

Applications rarely worry about bit-level corruption.
TCP absorbs that pain.

---

## Acknowledgements: Proof of Life
TCP doesn’t assume delivery.
It demands confirmation.

When a segment arrives correctly,
the receiver sends an **ACK**:

“I received everything up to sequence number X”

ACKs are cumulative:
- They confirm ranges, not individual packets
- This reduces network chatter

If ACKs stop arriving,
the sender assumes trouble.

---

## Retransmission: Fixing What the Network Broke
If a segment:
- Is lost
- Arrives corrupted
- Is not acknowledged within a timeout

TCP retransmits it.

But this is not reckless resending.

TCP uses:
- Retransmission timers
- Duplicate ACK detection
- Adaptive timeouts based on network conditions

Retransmission is precise, not panicked.

This is how TCP survives:
- Congested routers
- Flaky Wi-Fi
- Long-distance links
- Temporary outages

The network can fail.
The stream continues.

---

## Flow Control: Not Overwhelming the Receiver
Reliability without restraint would melt systems.

TCP includes **flow control**:
- Receiver advertises how much data it can handle
- Sender respects that window

This prevents:
- Buffer overflow
- Memory exhaustion
- Slow receivers being crushed by fast senders

Reliability without flow control
is denial-of-service against yourself.

---

## Congestion Control: Respecting the Network
TCP also watches the network itself.

When losses increase:
- TCP slows down
- Reduces send rate
- Gradually ramps back up

This prevents:
- Network collapse
- Congestion storms
- Unfair bandwidth usage

Congestion control is why
the internet doesn’t collapse every evening.

---

## Why UDP Skips All of This
UDP has:
- No segmentation management
- No error recovery
- No retransmission
- No flow control
- No congestion control

It sends and moves on.

This is not negligence.
It’s delegation.

Applications using UDP:
- Accept loss
- Implement their own recovery
- Or ignore errors entirely

Video calls don’t need perfect frames.
They need timely ones.

---

## The Architectural Truth
These mechanisms exist because
networks fail in boring, repetitive ways.

TCP doesn’t eliminate failure.
It **contains** it.

By segmenting data, checking errors,
acknowledging receipt, and retransmitting selectively,
TCP turns an unreliable substrate
into a reliable illusion.

Every time a large file downloads correctly
over bad Wi-Fi,
these mechanisms quietly did their job.

---

## One-Line Summary
**TCP doesn’t trust the network. It manages it.**