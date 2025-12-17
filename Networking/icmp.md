# ICMP (Internet Control Message Protocol) – Cybersecurity Focused Notes

## What is ICMP
ICMP (Internet Control Message Protocol) is a network-layer protocol used by devices to send error messages and operational information about IP packet delivery. ICMP does not transfer application data but supports network diagnostics and control.

ICMP operates at:
- Network Layer (Layer 3)
- Encapsulated within IP packets

ICMP does not use TCP or UDP ports.

---

## Why ICMP is Important in Cybersecurity
ICMP is used to:
- Discover live hosts
- Map network paths
- Detect unreachable systems
- Signal network errors

Attackers abuse ICMP for:
- Reconnaissance
- Firewall evasion
- Data exfiltration
- Denial-of-Service attacks

---

## Common ICMP Message Types (Security Relevant)

- Type 0 → Echo Reply
- Type 3 → Destination Unreachable
- Type 5 → Redirect
- Type 8 → Echo Request
- Type 11 → Time Exceeded

Understanding these ICMP message types is critical for effective traffic analysis and identifying potential malicious activities.

---

## ICMP Echo Request & Reply (Ping)
The `ping` utility leverages ICMP to test the reachability of a host on an IP network. It operates using the following message types:
- Echo Request (Type 8)
- Echo Reply (Type 0)

Command:
```bash
ping <IP>
```
This command sends ICMP Echo Requests to the specified IP address and waits for Echo Replies, providing insights into network latency and packet loss.

---

## ICMP and Traceroute
The `traceroute` utility uses ICMP (or sometimes UDP) to map the path packets take to reach a destination. It operates by sending packets with incrementally increasing TTL (Time-To-Live) values, eliciting ICMP Time Exceeded (Type 11) messages from intermediate routers.

Command:
```bash
traceroute <IP>
```
This command helps in diagnosing routing issues and understanding the network topology.
