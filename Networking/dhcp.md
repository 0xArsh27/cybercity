# DHCP (Dynamic Host Configuration Protocol) – Cybersecurity Focused Notes

## What is DHCP
DHCP (Dynamic Host Configuration Protocol) is a network protocol used to automatically assign IP configuration to devices on a network. It eliminates manual IP assignment and enables large-scale network management.

DHCP operates at:
- Application Layer
- Uses UDP transport

Default ports:
- UDP 67 → DHCP Server
- UDP 68 → DHCP Client

---

## Why DHCP is Critical in Cybersecurity
DHCP controls:
- IP address allocation
- Subnet mask
- Default gateway
- DNS servers

If DHCP is compromised, an attacker can:
- Redirect traffic
- Perform Man-in-the-Middle attacks
- Disrupt the entire network
- Spy on users silently

---

## DHCP Communication Process (DORA)
DHCP follows a four-step process called **DORA**:

1. **Discover**
   - Client broadcasts request for IP
   - Source IP: 0.0.0.0
   - Destination IP: 255.255.255.255

2. **Offer**
   - DHCP server offers an IP address

3. **Request**
   - Client requests the offered IP

4. **Acknowledge**
   - Server confirms assignment

This broadcast-based process is a major security weakness.

---

## DHCP Lease
A DHCP lease is a temporary assignment of an IP address.

- Lease time can be minutes, hours, or days
- After expiration, IP is reclaimed

Security relevance:
- Short leases → frequent reassignments
- Attribution becomes harder in incident response

---

## Information Provided by DHCP
DHCP can assign:
- IP address
- Subnet mask
- Default gateway
- DNS server
- Domain name
- NTP server

Malicious DHCP can manipulate **any of these**.

---

## DHCP in Real Networks

### Home Networks
- Router acts as DHCP server
- Devices receive private IPs (192.168.x.x)

### Enterprise Networks
- Centralized DHCP servers
- VLAN-based DHCP scopes
- DHCP relay agents

### Cloud Networks
- DHCP-like services assign private IPs
- Cloud metadata attacks depend on DHCP behavior

---

## DHCP Attacks (VERY IMPORTANT)

### Rogue DHCP Server Attack
Attacker introduces a fake DHCP server that:
- Assigns attacker-controlled gateway
- Redirects traffic through attacker
- Enables MITM and credential theft

This is one of the most dangerous LAN attacks.

---

### DHCP Starvation Attack
Attacker floods DHCP server with fake requests:
- Exhausts IP pool
- Legitimate clients cannot get IP
- Causes Denial of Service

Often followed by rogue DHCP attack.

---

### Man-in-the-Middle via DHCP
Attacker sets:
- Default gateway → attacker system
- DNS server → malicious DNS

Victims are unaware of compromise.

---

## DHCP and MITM Attack Chain
1. DHCP Starvation
2. Rogue DHCP Server
3. Gateway poisoning
4. DNS manipulation
5. Credential capture

This is a classic internal network attack chain.

---

## DHCP in Packet Analysis
In Wireshark:
- Use the filter: `dhcp` or `bootp`
- Analyze DORA packets, which are visible in plain text
- Trace IP assignments and identify anomalies

Applications:
- Incident investigation
- Detection of rogue DHCP servers
- Comprehensive network troubleshooting

For command-line analysis, use `tshark`:
```bash
tshark -i eth0 -Y "bootp" -V
```
This command captures and displays detailed DHCP traffic, aiding in forensic analysis and attack detection.

---

## DHCP Enumeration (Ethical Labs Only)
To monitor DHCP traffic, use the following `tcpdump` command:
```bash
tcpdump -i eth0 port 67 or port 68
```
Alternatively, for a more detailed analysis, use `tshark`:
```bash
tshark -i eth0 -f "port 67 or port 68" -V
```
These commands are essential for identifying DHCP activity and potential malicious behavior in a controlled lab environment.
