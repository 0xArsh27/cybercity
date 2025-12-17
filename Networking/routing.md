# Routing – Cybersecurity Focused Notes

## What is Routing
Routing is the process of selecting a path for network traffic to travel from a source network to a destination network. Routing is performed by routers and Layer-3 devices using routing tables and routing protocols.

Routing operates at:
- Network Layer (Layer 3)

Every packet leaving a subnet depends on routing decisions.

---

## Why Routing is Critical in Cybersecurity
Routing controls:
- Where traffic goes
- Which networks can communicate
- How traffic enters and exits an organization

If routing is compromised, attackers can:
- Redirect traffic
- Bypass security controls
- Intercept sensitive data
- Blackhole or drop traffic

---

## Routing Table
A routing table is a set of rules used to determine packet forwarding.

View routing table in Linux:
```bash
ip route
```

---

## Static Routing
Static routing involves manually configuring routing entries. It is simple and secure but lacks scalability. Static routes are often used in small networks or for specific, predictable traffic flows.

### Cybersecurity Implications:
- Provides predictable routing paths, reducing attack surface.
- Misconfigured static routes can lead to traffic blackholing or exposure.

Command to add a static route in Linux:
```bash
ip route add <destination> via <gateway>
```

---

## Dynamic Routing
Dynamic routing uses protocols to automatically adjust routes based on network changes. Common dynamic routing protocols include OSPF, BGP, and RIP.

### Cybersecurity Implications:
- Dynamic routing protocols can be targeted for route manipulation attacks (e.g., BGP hijacking).
- Proper authentication and encryption of routing protocol traffic are critical.

Example of enabling OSPF on a router:
```bash
router ospf
 network <IP> area <area-id>
```
