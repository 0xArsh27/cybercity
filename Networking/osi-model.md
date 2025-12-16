# OSI Model (Open Systems Interconnection)

The **OSI Model** is a **7-layer conceptual framework** that describes how data flows across a network. It is a foundational model in networking and cybersecurity, providing a structured approach to understanding and addressing network communication and security challenges.

> Think of the OSI Model as a **blueprint** for diagnosing and securing network systems.

---

## Importance of the OSI Model in Cybersecurity

- Identifies **attack surfaces** across layers.
- Maps **security tools and techniques** to specific layers.
- Facilitates **incident response and troubleshooting**.
- Essential for **packet analysis** and **network forensics**.
- Frequently referenced in **cybersecurity certifications** and **interviews**.

---

## OSI Model Layers (Top → Bottom)

| Layer | Name          | Key Responsibility |
|------|---------------|-------------------|
| 7 | Application | User-facing network services |
| 6 | Presentation | Data formatting, encryption, compression |
| 5 | Session | Session establishment and management |
| 4 | Transport | Reliable data transfer |
| 3 | Network | Logical addressing and routing |
| 2 | Data Link | MAC addressing and frame delivery |
| 1 | Physical | Transmission of raw bits |

Mnemonic: **All People Seem To Need Data Processing**

---

## Layer 7 – Application Layer

### Responsibilities
- Provides network services to applications.
- Interfaces directly with end-users.

### Examples
- HTTP / HTTPS
- FTP
- SMTP
- DNS
- SSH

### Cybersecurity Relevance
- Web-based attacks and vulnerabilities.

### Common Attacks
- SQL Injection
- Cross-Site Scripting (XSS)
- Cross-Site Request Forgery (CSRF)
- Command Injection

### Security Tools
- Burp Suite
- OWASP ZAP
- Nikto

---

## Layer 6 – Presentation Layer

### Responsibilities
- Data formatting and translation.
- Encryption and decryption.
- Data compression.

### Examples
- SSL / TLS
- JPEG, MP3 encoding

### Cybersecurity Relevance
- Ensures data confidentiality and integrity.

### Common Attacks
- SSL stripping
- Exploitation of weak encryption algorithms

### Security Tools
- OpenSSL
- Wireshark (TLS analysis)

---

## Layer 5 – Session Layer

### Responsibilities
- Establishes, manages, and terminates communication sessions.
- Maintains session state and synchronization.

### Examples
- Session IDs
- Authentication sessions

### Cybersecurity Relevance
- Vulnerable to session hijacking and fixation.

### Common Attacks
- Session fixation
- Session hijacking

---

## Layer 4 – Transport Layer

### Responsibilities
- End-to-end communication.
- Flow control, error detection, and reliability.

### Protocols
- TCP (Transmission Control Protocol)
- UDP (User Datagram Protocol)

### Cybersecurity Relevance
- Focus of port scanning and denial-of-service (DoS) attacks.

### Common Attacks
- SYN flood
- UDP flood

### Security Tools
- Nmap
- Netcat
- Wireshark

---

## Layer 3 – Network Layer

### Responsibilities
- Logical addressing and routing of packets.
- Handles IP addressing and path determination.

### Examples
- IP (IPv4 / IPv6)
- ICMP (Internet Control Message Protocol)

### Cybersecurity Relevance
- Network mapping and routing-based attacks.

### Common Attacks
- IP spoofing
- ICMP tunneling

### Security Tools
- Traceroute
- Ping
- Nmap

---

## Layer 2 – Data Link Layer

### Responsibilities
- MAC addressing and frame delivery within a LAN.
- Error detection and correction.

### Examples
- ARP (Address Resolution Protocol)
- Ethernet
- Switches

### Cybersecurity Relevance
- LAN-based attacks and vulnerabilities.

### Common Attacks
- ARP spoofing
- MAC flooding

### Security Tools
- Ettercap
- Bettercap
- Wireshark

---

## Layer 1 – Physical Layer

### Responsibilities
- Transmission of raw bits over a physical medium.
- Defines hardware specifications.

### Examples
- Cables
- Signals
- Network interface cards (NICs)

### Cybersecurity Relevance
- Physical security and hardware-based attacks.

### Common Attacks
- Cable tapping
- Hardware keyloggers

---

## OSI Layers Mapped to Cybersecurity Tools

| Tool         | OSI Layer       |
|--------------|-----------------|
| Burp Suite   | Layer 7         |
| OWASP ZAP    | Layer 7         |
| Wireshark    | Layers 2–7      |
| Nmap         | Layers 3–4      |
| Metasploit   | Layers 4–7      |
| Firewall     | Layers 3–4      |
| WAF          | Layer 7         |
| IDS / IPS    | Layers 3–7      |

---

## OSI Model vs TCP/IP Model

| OSI Model | TCP/IP Model |
|-----------|--------------|
| 7 layers  | 4 layers     |
| Theoretical | Practical   |
| Detailed  | Simplified   |

### TCP/IP Layers
- Application
- Transport
- Internet
- Network Access

---

## Interview Tips

- Most web attacks → **Layer 7**
- Port scanning → **Layer 4**
- ARP spoofing → **Layer 2**
- Firewalls operate at **Layers 3 & 4**
- WAFs operate at **Layer 7**

---

## Summary

- The OSI Model is a critical framework for understanding **network communication and security**.
- Each layer has **unique vulnerabilities and defenses**.
- Mastery of the OSI Model is essential for **cybersecurity professionals** to effectively secure and troubleshoot networks.

> "Understanding the OSI Model is not just about networking—it’s about securing the digital world."

