# TCP & UDP – Cybersecurity Focused Notes

## Overview of TCP and UDP
TCP (Transmission Control Protocol) and UDP (User Datagram Protocol) are critical Layer 4 (Transport Layer) protocols in both the OSI and TCP/IP models. They govern how data is transmitted between devices over a network. 

In the realm of cybersecurity, a deep understanding of TCP and UDP is essential for:
- Conducting port scans to identify open services.
- Exploiting vulnerabilities in network protocols.
- Analyzing network traffic for anomalies.
- Configuring firewalls and intrusion prevention systems.
- Detecting malware communication patterns.
- Responding to security incidents effectively.

---

## TCP (Transmission Control Protocol)

### Key Characteristics
- **Connection-Oriented**: Establishes a reliable connection before data transfer.
- **Reliable Data Transfer**: Ensures all data is delivered accurately.
- **Ordered Delivery**: Maintains the sequence of transmitted packets.
- **Error Checking**: Detects and retransmits lost or corrupted packets.
- **Performance**: Slower than UDP but prioritizes reliability.

---

## TCP Three-Way Handshake
TCP establishes a connection using a three-step process:

1. **SYN** → Client initiates a connection request.
2. **SYN-ACK** → Server acknowledges the request.
3. **ACK** → Client confirms the connection.

### Cybersecurity Relevance
- **Packet Analysis**: Tools like Wireshark capture and analyze handshake packets.
- **Intrusion Detection**: IDS/IPS monitor handshake anomalies.
- **Attack Vector**: SYN flood attacks exploit this process to overwhelm servers.

---

## TCP Flags (Critical for Security)
TCP uses flags to manage connections and data flow.

### Common Flags
- **SYN**: Initiates a connection.
- **ACK**: Acknowledges received data.
- **FIN**: Gracefully terminates a connection.
- **RST**: Abruptly terminates a connection.
- **PSH**: Pushes data immediately.
- **URG**: Indicates urgent data.

### Security Implications
- **SYN Floods**: Exploit the SYN flag to exhaust server resources.
- **RST Injection**: Terminates legitimate connections maliciously.
- **FIN Scans**: Used in stealthy reconnaissance.

---

## Common TCP Ports (High-Value Targets)

- **21** → FTP
- **22** → SSH
- **23** → Telnet
- **25** → SMTP
- **80** → HTTP
- **443** → HTTPS
- **445** → SMB
- **3389** → RDP

### Cybersecurity Context
- Frequently scanned by attackers to identify vulnerabilities.
- Monitored by Security Operations Centers (SOC) for suspicious activity.
- Targeted in exploits to gain unauthorized access.

---

## TCP-Based Attacks

### SYN Flood
- **Mechanism**: Sends numerous SYN packets without completing the handshake.
- **Impact**: Exhausts server resources, leading to Denial of Service (DoS).

### Session Hijacking
- **Mechanism**: Predicts or steals TCP sequence numbers to take over a session.
- **Impact**: Enables unauthorized access to active connections.

### TCP Reset Attack
- **Mechanism**: Sends forged RST packets to terminate connections.
- **Impact**: Disrupts legitimate communication.

---

## Defensive Measures for TCP
- **Stateful Firewalls**: Track TCP connection states to block unauthorized access.
- **Intrusion Detection Systems (IDS)**: Detect abnormal flag patterns.
- **Security Information and Event Management (SIEM)**: Correlate TCP session data across logs.

---

## UDP (User Datagram Protocol)

### Key Characteristics
- **Connectionless**: No handshake required.
- **Unreliable Delivery**: No guarantees for data delivery.
- **No Retransmission**: Lost packets are not resent.
- **Performance**: Faster than TCP, prioritizing speed over reliability.

---

## Common UDP Ports (Security-Relevant)

- **53** → DNS
- **67/68** → DHCP
- **69** → TFTP
- **123** → NTP
- **161** → SNMP
- **500** → ISAKMP (VPN)

### Cybersecurity Context
- Misconfigured UDP services are common attack vectors.
- UDP-based services are often exploited in amplification attacks.

---

## UDP-Based Attacks

### UDP Flood
- **Mechanism**: Sends a high volume of UDP packets to overwhelm the target.
- **Impact**: Consumes bandwidth, causing Denial of Service (DoS).

### DNS Amplification
- **Mechanism**: Sends small DNS queries with spoofed IPs to generate large responses.
- **Impact**: Amplifies traffic, leading to high-impact Distributed Denial of Service (DDoS).

### NTP Amplification
- **Mechanism**: Exploits misconfigured NTP servers to amplify traffic.
- **Impact**: Generates massive traffic, overwhelming the target.

---

## UDP in Reconnaissance
- **Challenges**: Harder to scan due to the lack of a handshake.
- **Tools**: Nmap UDP scans are slower but effective.
- **Firewall Considerations**: Many firewalls allow UDP traffic by default, increasing risk.

### Example Command
```bash
nmap -sU 192.168.1.0/24
```

### Cybersecurity Tip
- Use rate-limiting and anomaly detection to mitigate UDP-based reconnaissance and attacks.
