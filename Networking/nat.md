# NAT (Network Address Translation) – Cybersecurity Focused Notes

## What is NAT
NAT (Network Address Translation) is a technique used to modify IP address information in packet headers while traffic is in transit. NAT allows multiple private devices to share a single public IP address when accessing external networks.

NAT operates at:
- Network Layer (Layer 3)
- Transport Layer (Layer 4) when ports are translated

---

## Why NAT is Important in Cybersecurity
NAT provides:
- IP address conservation
- Internal network masking
- Basic exposure reduction

However, NAT is **not a security control** by itself and should not be confused with a firewall.

---

## Why NAT Exists
- IPv4 address exhaustion
- Large number of private networks
- Need to access the internet using limited public IPs

Almost every home, enterprise, and cloud network uses NAT.

---

## Types of NAT (Security Relevant)

### Static NAT
- One-to-one mapping
- One private IP ↔ one public IP
- Common for servers

Security impact:
- Predictable target
- Increased exposure

---

### Dynamic NAT
- Many private IPs ↔ pool of public IPs
- Mapping changes dynamically

Security impact:
- Harder attribution
- Reduced predictability

---

### PAT / NAPT (Port Address Translation)
- Many private IPs ↔ single public IP
- Uses port numbers to track sessions
- Most common NAT type

Security impact:
- Hides internal structure
- Complicates inbound connections

---

## NAT Table
NAT devices maintain a translation table.

Contains:
- Private IP
- Private port
- Public IP
- Public port
- Protocol

Security relevance:
- Session tracking
- Forensics and investigations
- Malware C2 communication analysis

---

## NAT and Private IP Addresses
NAT is commonly used with:
- 10.0.0.0/8
- 172.16.0.0/12
- 192.168.0.0/16

Private IPs are not routable on the internet.

---

## NAT and Outbound Traffic
- Internal devices can initiate outbound connections
- NAT creates temporary mappings
- Return traffic is allowed automatically

Security insight:
Outbound traffic is often less restricted and abused by malware.

---

## NAT and Inbound Traffic
- Inbound traffic is blocked by default
- Requires port forwarding or static NAT

Security risk:
Port forwarding exposes internal services directly to the internet.

---

## Port Forwarding (VERY IMPORTANT)
Port forwarding maps:
- Public IP + port → Private IP + port

Example:
- Public: 203.0.113.10:22
- Private: 192.168.1.10:22

Security risks:
- Exposed SSH, RDP, web services
- Common attack vector

---

## NAT and Firewalls (IMPORTANT DISTINCTION)
NAT:
- Translates addresses
- Does NOT inspect traffic content

Firewall:
- Filters traffic based on rules
- Enforces security policies

NAT ≠ Firewall

---

## NAT in Cyber Attacks

### Malware Command and Control (C2)
- Malware uses outbound connections
- NAT allows easy egress
- Hard to block without egress filtering

---

### NAT Slipstreaming
- Browser-based attack
- Bypasses NAT using protocol manipulation
- Opens internal ports without user knowledge

---

### Attribution Challenges
- Multiple users share one public IP
- Harder to identify attacker
- Common in ISP and corporate environments

---

## NAT and Logging (SOC Perspective)
SOC teams rely on:
- NAT logs
- DHCP logs
- Firewall logs

To map:
Public IP → Private IP → User

Without NAT logs, attribution is almost impossible.

---

## NAT and VPNs
VPNs manipulate NAT behavior:
- NAT traversal (NAT-T)
- UDP encapsulation
- Split vs full tunneling

Security risk:
- VPN route leaks
- Traffic bypassing security controls

---

## NAT Traversal Techniques
Used by:
- VPNs
- VoIP
- P2P applications

Examples:
- STUN
- TURN
- ICE

Attackers abuse these to bypass network restrictions.

---

## NAT in Cloud Environments
Cloud NAT is used to:
- Provide internet access to private instances
- Hide internal workloads

Misconfigured NAT can:
- Expose private services
- Enable data exfiltration

---

## NAT and IPv6 (Security Note)
IPv6 reduces the need for NAT:
- Public IP per device
- Shifts security responsibility to firewalls

Many security teams still rely on NAT-style thinking, which is dangerous in IPv6 networks.

---

## Defensive Controls Around NAT
- Minimize port forwarding
- Use firewall rules with NAT
- Monitor NAT table usage
- Log NAT translations
- Implement egress filtering

---

## NAT in Incident Response
Investigators analyze:
- NAT mappings
- Session times
- Source ports

To:
- Trace attacks
- Identify compromised hosts
- Correlate user activity

---

## Key Cybersecurity Takeaway
NAT is not security — it is **address translation**.

Mastering NAT allows you to:
- Understand real-world network exposure
- Track attackers behind shared IPs
- Detect malware communication
- Secure home, enterprise, and cloud networks
- Perform accurate SOC investigations
