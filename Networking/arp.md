# ARP (Address Resolution Protocol) – Cybersecurity Focused Notes

## What is ARP
ARP (Address Resolution Protocol) is a fundamental network protocol used to resolve IP addresses to MAC addresses within a local network. Since communication on a LAN relies on MAC addresses, ARP ensures devices can locate the correct physical address for an IP.

ARP operates at the intersection of:
- **Network Layer (IP)**
- **Data Link Layer (MAC)**

### Security Implications
ARP lacks authentication mechanisms, making it inherently vulnerable to exploitation. This absence of security controls is a critical weakness in modern networks.

---

## Why ARP is Critical in Cybersecurity
ARP plays a pivotal role in network communication by determining:
- The identity of the gateway
- The destination of network traffic
- The recipient of data packets

### Potential Risks
If ARP is compromised, attackers can:
- Intercept sensitive traffic
- Modify or inject malicious data
- Redirect communication to malicious endpoints
- Execute Man-in-the-Middle (MITM) attacks covertly

---

## How ARP Works
1. A device intending to send data to an IP address checks its ARP cache for the corresponding MAC address.
2. If the mapping is unavailable, it broadcasts an ARP request:
   - **Message:** “Who has IP X.X.X.X? Tell me your MAC.”
3. The device with the requested IP responds with its MAC address.
4. The mapping is stored in the ARP cache for future use.

### Security Weakness
This broadcast-based, trust-dependent mechanism is inherently insecure and susceptible to spoofing attacks.

---

## ARP Request vs ARP Reply

### ARP Request
- **Type:** Broadcast
- **Scope:** Sent to all devices in the subnet
- **Purpose:** Requests the MAC address for a specific IP

### ARP Reply
- **Type:** Unicast
- **Scope:** Sent directly to the requesting device
- **Purpose:** Provides the IP–MAC mapping

### Exploitation
Attackers exploit ARP replies to inject malicious mappings into ARP caches, enabling traffic interception and redirection.

---

## ARP Cache
Each device maintains an ARP table (cache) that stores IP-to-MAC mappings. These entries are temporary and expire after a predefined duration.

### Viewing ARP Cache
On Windows systems, use the following command to view the ARP cache:
```bash
arp -a
```

### Security Considerations
- **Cache Poisoning:** Attackers can inject false entries into the ARP cache, redirecting traffic to malicious devices.
- **Mitigation:** Employ dynamic ARP inspection (DAI) and static ARP entries where feasible.
