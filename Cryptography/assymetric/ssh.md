=====================================
SSH (SECURE SHELL) – CYBERSECURITY NOTES
=====================================

SSH (Secure Shell) is a cryptographic network protocol used to securely access, manage, and transfer data between systems over an insecure network. It provides encrypted communication, strong authentication, and integrity protection.

-------------------------------------
WHY SSH IS NEEDED
-------------------------------------
Older remote access protocols like Telnet transmit data (including passwords) in plaintext.
SSH replaces them by providing:
- Encrypted communication
- Secure authentication
- Protection against eavesdropping and MITM attacks

-------------------------------------
DEFAULT DETAILS
-------------------------------------
Protocol: SSH
Default Port: 22/TCP
Layer: Application Layer
Transport: TCP

-------------------------------------
CORE SECURITY GOALS OF SSH
-------------------------------------
- Confidentiality (encryption)
- Integrity (message authentication)
- Authentication (user and server verification)

-------------------------------------
SSH ARCHITECTURE (3 MAIN COMPONENTS)
-------------------------------------
1. Transport Layer
   - Handles encryption and integrity
   - Uses symmetric encryption (AES)
   - Uses key exchange (Diffie–Hellman / ECDH)

2. Authentication Layer
   - Verifies user identity
   - Password-based or key-based authentication

3. Connection Layer
   - Manages multiple channels
   - Supports port forwarding and file transfer

-------------------------------------
SSH CONNECTION PROCESS (STEP BY STEP)
-------------------------------------
1. Client initiates SSH connection to server
2. Server sends its public key
3. Client verifies server identity (known_hosts)
4. Key exchange occurs (Diffie–Hellman / ECDH)
5. Secure symmetric session key is generated
6. User authentication happens
7. Encrypted session starts

-------------------------------------
SSH AUTHENTICATION METHODS
-------------------------------------

1. PASSWORD-BASED AUTHENTICATION
- User enters username and password
- Vulnerable to brute-force attacks
- Not recommended for production systems

2. KEY-BASED AUTHENTICATION (RECOMMENDED)
- Uses public/private key pair
- Private key stays on client
- Public key stored on server

-------------------------------------
SSH-KEYGEN (KEY GENERATION COMMAND)
-------------------------------------
ssh-keygen is used to generate SSH key pairs for secure key-based authentication.

Basic Command:
ssh-keygen

What it does:
- Generates a public and private key pair
- Stores keys in ~/.ssh/ directory by default

Generated Files:
- id_rsa        → Private key (KEEP SECRET)
- id_rsa.pub    → Public key (shared with server)

-------------------------------------
COMMON SSH-KEYGEN OPTIONS
-------------------------------------
Generate RSA key (default):
ssh-keygen -t rsa

Generate strong RSA key:
ssh-keygen -t rsa -b 4096

Generate Ed25519 key (modern & recommended):
ssh-keygen -t ed25519

Specify key file name:
ssh-keygen -t rsa -f my_ssh_key

Add passphrase (highly recommended):
ssh-keygen -t ed25519 -C "my_email@example.com"

-------------------------------------
ADDING PUBLIC KEY TO SERVER
-------------------------------------
Method 1 (Recommended):
ssh-copy-id user@ip_address

Method 2 (Manual):
- Copy contents of id_rsa.pub
- Paste into server file:
  ~/.ssh/authorized_keys

-------------------------------------
SSH KEY-BASED AUTHENTICATION FLOW
-------------------------------------
1. Client generates key pair using ssh-keygen
2. Public key is added to server
3. Client proves possession of private key
4. Server verifies and grants access

No password is transmitted over the network.

-------------------------------------
COMMON SSH COMMANDS (CYBERSECURITY USE)
-------------------------------------
Connect to server:
ssh user@ip_address

Connect with specific port:
ssh -p 2222 user@ip_address

Login using private key:
ssh -i private_key.pem user@ip_address

Secure file copy (SCP):
scp file.txt user@ip:/path/

Secure file transfer (SFTP):
sftp user@ip_address

-------------------------------------
SSH PORT FORWARDING (TUNNELING)
-------------------------------------
SSH can securely tunnel traffic.

Types:
- Local Port Forwarding
- Remote Port Forwarding
- Dynamic Port Forwarding (SOCKS proxy)

Use cases:
- Secure access to internal services
- Firewall bypassing
- Pivoting during penetration testing

-------------------------------------
SSH IN REAL CYBERSECURITY ROLES
-------------------------------------
SOC Analyst:
- Detect SSH brute-force attacks
- Monitor failed authentication logs

DFIR:
- Investigate unauthorized SSH access
- Identify compromised SSH keys

Blue Team:
- Enforce key-based authentication
- Disable password login
- Rotate SSH keys

Red Team:
- SSH brute-force
- Key abuse
- SSH tunneling for lateral movement

-------------------------------------
COMMON SSH ATTACKS
-------------------------------------
- Brute-force login attempts
- Credential stuffing
- Stolen private keys
- MITM (if host verification ignored)

-------------------------------------
SSH HARDENING BEST PRACTICES
-------------------------------------
- Disable root login
- Disable password authentication
- Use ssh-keygen with strong keys
- Protect private keys with passphrase
- Restrict SSH access by IP
- Enable fail2ban
- Monitor auth logs

-------------------------------------
IMPORTANT SSH FILES (LINUX)
-------------------------------------
/etc/ssh/sshd_config   → SSH server configuration
~/.ssh/authorized_keys → Allowed public keys
~/.ssh/known_hosts     → Trusted server keys
/var/log/auth.log      → SSH authentication logs

-------------------------------------
SSH MINDSET
-------------------------------------
ssh-keygen is the foundation of secure SSH.
If private keys are leaked → security fails.
Protect keys like passwords, or even better.
