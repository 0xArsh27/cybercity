# TCP/IP Model (Transmission Control Protocol / Internet Protocol)

The **TCP/IP model** is the **practical networking model used in the real world and on the Internet**. Unlike the OSI model (theoretical), TCP/IP defines **how data actually moves across networks** and is foundational for modern cybersecurity practices.

In cybersecurity, TCP/IP is critical for:
- **Network traffic analysis**
- **Attack detection and prevention**
- **Exploitation and defense strategies**
- **Incident response and forensics**

---

## Why TCP/IP Model is Important in Cybersecurity

- **Widely used** in real-world networks and the Internet.
- Helps understand **packet flow and behavior**.
- Essential for tools like **Wireshark, Nmap, and Metasploit**.
- Directly related to **cyber attacks, logs, and defenses**.
- Frequently referenced in **cybersecurity certifications and interviews**.

> OSI explains *concepts*, TCP/IP explains *reality*.

---

## TCP/IP Model Layers (4 Layers)

| TCP/IP Layer    | Equivalent OSI Layers |
|-----------------|------------------------|
| Application     | OSI Layers 7, 6, 5    |
| Transport       | OSI Layer 4           |
| Internet        | OSI Layer 3           |
| Network Access  | OSI Layers 2, 1       |

---

## 1️⃣ Application Layer

### Responsibilities
- Provides network services to applications.
- Combines OSI Application, Presentation, and Session layers.

### Common Protocols
- HTTP / HTTPS
- FTP
- SMTP / POP3 / IMAP
- DNS
- SSH

### Cybersecurity Relevance
- **Most attacks occur here** due to user interaction and data exchange.

### Common Attacks
- SQL Injection (SQLi)
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- File upload vulnerabilities
- Phishing

### Security Tools
- Burp Suite
- OWASP ZAP
- Nikto
- Gobuster

---

## 2️⃣ Transport Layer

### Responsibilities
- End-to-end communication.
- Port numbers for application identification.
- Flow control, reliability, and error handling.

### Protocols
- TCP (Transmission Control Protocol)
- UDP (User Datagram Protocol)

---

### TCP (Transmission Control Protocol)

#### Key Features
- Connection-oriented.
- Reliable and ensures ordered delivery.
- Error checking and retransmission.

#### TCP 3-Way Handshake
1. SYN (Synchronize)
2. SYN-ACK (Synchronize-Acknowledge)
3. ACK (Acknowledge)

#### Cybersecurity Importance
- Focus of port scanning and session tracking.
- Critical for traffic inspection and analysis.

#### Common Attacks
- SYN Flood
- TCP Session Hijacking
- RST Injection

---

### UDP (User Datagram Protocol)

#### Key Features
- Connectionless and faster.
- No reliability or ordered delivery.
- Suitable for time-sensitive applications.

#### Use Cases
- DNS
- VoIP
- Streaming
- Online gaming

#### Common Attacks
- UDP Flood
- Amplification attacks (e.g., DNS, NTP)

---

### Security Tools (Transport Layer)
- Nmap
- Netcat
- Wireshark
- Metasploit

---

## 3️⃣ Internet Layer

### Responsibilities
- Logical addressing and routing of packets.
- Ensures data reaches the correct destination.

### Protocols
- IP (IPv4, IPv6)
- ICMP (Internet Control Message Protocol)
- IPsec (Internet Protocol Security)

---

### IP (Internet Protocol)

#### Responsibilities
- Assigns source and destination IP addresses.
- Handles packet fragmentation and routing.

#### Common Attacks
- IP Spoofing
- Packet injection
- Tunneling

---

### ICMP

#### Purpose
- Error reporting and network diagnostics.

#### Examples
- Ping
- Traceroute

#### Common Attacks
- ICMP Flood
- ICMP Tunneling

---

### Security Tools
- Ping
- Traceroute
- Nmap
- Wireshark

---

## 4️⃣ Network Access Layer

### Responsibilities
- Physical transmission of data.
- MAC addressing and frame delivery within a LAN.

### Equivalent OSI Layers
- Data Link (Layer 2)
- Physical (Layer 1)

### Technologies
- Ethernet
- Wi-Fi
- ARP (Address Resolution Protocol)
- Switches

---

### Cybersecurity Relevance
- Focus of local network attacks and hardware vulnerabilities.

### Common Attacks
- ARP Spoofing
- MAC Flooding
- Evil Twin (Wi-Fi)

### Security Tools
- Ettercap
- Bettercap
- Aircrack-ng
- Wireshark

---

## TCP/IP vs OSI Model (Quick Comparison)

| Feature              | TCP/IP       | OSI            |
|----------------------|--------------|----------------|
| Layers               | 4            | 7              |
| Nature               | Practical    | Theoretical    |
| Used in real networks| Yes          | No             |
| Focus                | Implementation | Concept       |

---

## TCP/IP Layers Mapped to Cyber Attacks

| Attack              | TCP/IP Layer  |
|---------------------|---------------|
| XSS / SQLi          | Application   |
| SYN Flood           | Transport     |
| IP Spoofing         | Internet      |
| ARP Spoofing        | Network Access|

---

## TCP/IP & Security Devices

| Device              | Layer         |
|---------------------|---------------|
| Firewall            | Transport / Internet |
| WAF                 | Application   |
| IDS / IPS           | Internet – Application |
| VPN                 | Internet / Transport |

---

## Interview Tips

- TCP/IP is **used in real networks**.
- Most scanning → **Transport layer**.
- Routing & IP → **Internet layer**.
- LAN attacks → **Network Access layer**.
- Web attacks → **Application layer**.

---

## Summary

- TCP/IP is the **real-world networking model**.
- Every packet follows these 4 layers.
- Cyber attacks and defenses map directly to TCP/IP.
- Mastering TCP/IP = strong cybersecurity foundation.

> "If you understand TCP/IP, tools like Wireshark and Nmap become easy."

