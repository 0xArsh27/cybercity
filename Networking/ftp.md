# FTP (File Transfer Protocol) – Cybersecurity Focused Notes

## What is FTP
FTP (File Transfer Protocol) is an application-layer protocol used to transfer files between a client and a server over a network. FTP uses separate control and data channels and does not encrypt data by default.

Default ports:
- **TCP 21** → Control channel
- **TCP 20** → Data channel (Active mode)

---

## Why FTP is Important in Cybersecurity
FTP is often:
- Misconfigured
- Exposed to the internet
- Used in legacy systems

If compromised, attackers can:
- Steal sensitive files
- Upload malware or web shells
- Abuse anonymous access
- Move laterally inside networks

---

## FTP Architecture (Control vs Data Channel)

### Control Channel
- Used for authentication and commands
- Always over TCP 21
- Persistent connection

### Data Channel
- Used for file transfer
- Opened dynamically
- Major security concern

---

## FTP Modes (Security Critical)

### Active Mode
- Client opens control channel
- Server opens data connection back to client
- Requires client to accept incoming connections

**Security Risks:**
- Firewall issues
- Client exposure

---

### Passive Mode
- Client opens both control and data connections
- Server provides a random port

**Security Risks:**
- Wide port range exposure
- Misconfigured firewalls

Passive mode is more common today.

---

## FTP Authentication

### Normal Authentication
- Username and password sent in clear text
- Easily sniffed

### Anonymous FTP
- Allows login without credentials
- Common in public file repositories

**Security Risks:**
- Unauthorized access to sensitive files
- Abuse for malware distribution

---

## Common FTP Commands

### Basic Commands
- **`ftp <hostname>`** → Connect to an FTP server
- **`open <hostname>`** → Open a connection to the server
- **`user <username>`** → Provide username for authentication
- **`ls`** → List files in the current directory
- **`cd <directory>`** → Change directory
- **`get <filename>`** → Download a file
- **`put <filename>`** → Upload a file
- **`bye`** → Close the FTP session

### Advanced Commands
- **`passive`** → Enable passive mode
- **`active`** → Enable active mode
- **`mget <files>`** → Download multiple files
- **`mput <files>`** → Upload multiple files
- **`!`** → Escape to the local shell
- **`hash`** → Display transfer progress

---

## Defensive Measures
- Use **SFTP** or **FTPS** for encrypted file transfers.
- Disable anonymous FTP access.
- Restrict access to specific IPs using firewall rules.
- Monitor FTP logs for suspicious activity.
- Enforce strong authentication mechanisms.
- Regularly update and patch FTP servers.

---

## Key Cybersecurity Takeaway
FTP is a legacy protocol with inherent security risks. Transitioning to secure alternatives like SFTP or FTPS, combined with robust configurations and monitoring, is essential to mitigate threats.
