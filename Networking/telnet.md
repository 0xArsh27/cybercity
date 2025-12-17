# Telnet – Cybersecurity Focused Notes

## What is Telnet
Telnet is a network protocol used to remotely access and manage devices over a network. It operates at the Application Layer and uses TCP for communication.

Telnet provides a command-line interface to a remote system but **does not encrypt data**, making it insecure.

Default port:
- TCP 23

---

## How Telnet Works
1. Client initiates a TCP connection to port 23
2. Server accepts the connection
3. User credentials and commands are sent in plain text
4. Remote system executes commands and sends responses

No encryption or authentication protection is provided.

---

## Why Telnet is Insecure
- Usernames are transmitted in clear text
- Passwords are transmitted in clear text
- Commands and outputs are readable by anyone sniffing the network
- Vulnerable to Man-in-the-Middle (MITM) attacks

Anyone capturing traffic can fully compromise the session.

---

## Telnet in Cybersecurity Context
Telnet is rarely used legitimately today but is still:
- Found in legacy systems
- Present in IoT devices
- Used in intentionally vulnerable labs and CTFs
- A major red flag in security audits

---

## Telnet vs SSH
Telnet:
- No encryption
- Credentials visible
- Not secure
- Deprecated

SSH:
- Encrypted communication
- Secure authentication
- Integrity protected
- Industry standard replacement

---

## Telnet in Reconnaissance
Open Telnet port indicates:
- Legacy system
- Weak security posture
- Potential misconfiguration

Common scan:
```bash
nmap -p 23 <target>
```

---

## Common Telnet Commands for Cybersecurity

### Connecting to a Remote Host
```bash
telnet <target_ip> <port>
```
- **Purpose**: Establishes a Telnet session with the target.
- **Use Case**: Test if a specific port is open and accepting connections.

### Sending Custom Data to a Port
```bash
echo "<data>" | telnet <target_ip> <port>
```
- **Purpose**: Sends custom data to a specific port.
- **Use Case**: Test how a service responds to specific inputs.

### Banner Grabbing
```bash
telnet <target_ip> <port>
```
- **Purpose**: Retrieve service banners to identify software versions.
- **Use Case**: Enumerate services and detect vulnerabilities.

### Testing SMTP Servers
```bash
telnet <target_ip> 25
HELO example.com
MAIL FROM: <attacker@example.com>
RCPT TO: <victim@example.com>
DATA
Subject: Test
This is a test email.
.
QUIT
```
- **Purpose**: Interact with an SMTP server to test email functionality.
- **Use Case**: Identify open relays or misconfigurations.

### Interacting with HTTP Services
```bash
telnet <target_ip> 80
GET / HTTP/1.1
Host: <target_ip>

```
- **Purpose**: Send HTTP requests manually.
- **Use Case**: Test for HTTP vulnerabilities or misconfigurations.

### Testing Open Ports
```bash
telnet <target_ip> <port>
```
- **Purpose**: Check if a specific port is open.
- **Use Case**: Identify services running on non-standard ports.

### Closing a Telnet Session
```bash
CTRL+]
quit
```
- **Purpose**: Gracefully terminate a Telnet session.
- **Use Case**: Ensure proper disconnection after testing.

---

## Cybersecurity Tips for Using Telnet
- **Use in Isolated Environments**: Only use Telnet in controlled labs or testing environments.
- **Monitor Traffic**: Use packet capture tools like Wireshark to analyze Telnet sessions.
- **Avoid Sensitive Data**: Never transmit sensitive information over Telnet.
- **Replace with SSH**: Use SSH for secure remote access in production environments.
