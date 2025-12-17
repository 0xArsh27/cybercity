# SSH (Secure Shell) – Cybersecurity Focused Notes

## What is SSH
SSH (Secure Shell) is an application-layer protocol used to securely access and manage remote systems over an encrypted connection. SSH replaces insecure protocols like Telnet by providing confidentiality, integrity, and authentication.

Default port:
- **TCP 22**

SSH is widely used for:
- Remote server administration
- Secure file transfer
- Tunneling and port forwarding
- Cloud and DevOps operations

---

## Why SSH is Critical in Cybersecurity
SSH protects:
- Credentials
- Commands
- File transfers
- Administrative access

If SSH is compromised, attackers can:
- Gain full system control
- Perform lateral movement
- Maintain persistence
- Exfiltrate sensitive data

SSH access often equals **total compromise**.

---

## How SSH Works (High-Level)
1. Client initiates connection to SSH server.
2. Server presents its public host key.
3. Client verifies server identity.
4. Authentication occurs (password or key-based).
5. Encrypted session is established.

All communication is encrypted after the handshake.

---

## SSH Authentication Methods

### Password Authentication
- Username + password
- Vulnerable to brute force
- Common target for attackers

---

### Key-Based Authentication (BEST PRACTICE)
- Uses public/private key pair
- Private key stays with client
- Public key stored on server

Much stronger than passwords.

---

## SSH Key Files
- `id_rsa` → Private key (must be protected)
- `id_rsa.pub` → Public key

Permissions matter:
```bash
chmod 600 id_rsa
```

---

## Frequently Used SSH Commands

### Basic Commands
- **Connect to a remote server:**
  ```bash
  ssh user@hostname
  ```
- **Specify a custom port:**
  ```bash
  ssh -p <port> user@hostname
  ```
- **Run a command on a remote server:**
  ```bash
  ssh user@hostname "command"
  ```
- **Copy files to a remote server:**
  ```bash
  scp file.txt user@hostname:/path/to/destination
  ```
- **Copy files from a remote server:**
  ```bash
  scp user@hostname:/path/to/file.txt /local/path
  ```

### Advanced Commands
- **Generate SSH key pair:**
  ```bash
  ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
  ```
- **Add private key to SSH agent:**
  ```bash
  ssh-add ~/.ssh/id_rsa
  ```
- **Forward a local port to a remote server:**
  ```bash
  ssh -L local_port:remote_host:remote_port user@hostname
  ```
- **Forward a remote port to the local machine:**
  ```bash
  ssh -R remote_port:local_host:local_port user@hostname
  ```
- **Check SSH server version:**
  ```bash
  ssh -V
  ```
- **Copy SSH public key to a server:**
  ```bash
  ssh-copy-id user@hostname
  ```

---

## Defensive Measures
- Use key-based authentication instead of passwords.
- Disable root login via SSH.
- Change the default SSH port to reduce automated attacks.
- Enforce strong SSH key permissions.
- Monitor SSH logs for suspicious activity.
- Use fail2ban or similar tools to block brute-force attempts.
- Implement two-factor authentication (2FA) for SSH access.

---

## Key Cybersecurity Takeaway
SSH is a critical tool for secure remote access and management. Proper configuration, strong authentication mechanisms, and regular monitoring are essential to prevent unauthorized access and ensure the integrity of remote systems.
