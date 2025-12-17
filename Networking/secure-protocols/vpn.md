# VPN (Virtual Private Network) – Cybersecurity Focused Notes

## What is a VPN
A VPN (Virtual Private Network) creates an encrypted tunnel between a client and a remote network over an untrusted network (such as the internet). VPNs provide secure remote access and private communication.

VPNs are widely used in:
- Corporate remote access
- Cloud connectivity
- Secure site-to-site communication
- Privacy protection

---

## Why VPN is Critical in Cybersecurity
VPNs protect:
- Data in transit
- Internal network access
- Authentication credentials
- Remote workforce communication

If VPN is misconfigured or compromised, attackers can:
- Bypass perimeter defenses
- Access internal networks directly
- Move laterally across systems
- Maintain stealthy persistence

VPN compromise often equals **full internal network access**.

---

## How VPN Works (High-Level)
1. Client initiates VPN connection.
2. Authentication occurs (password, certificate, MFA).
3. Encrypted tunnel is established.
4. Traffic is routed through the tunnel.
5. VPN server forwards traffic to internal networks.

VPN modifies routing tables dynamically.

---

## Types of VPNs

### Remote Access VPN
- Individual user connects to corporate network.
- Common for work-from-home employees.

Security risks:
- Compromised credentials
- Unsecured endpoints

---

### Site-to-Site VPN
- Connects two networks together.
- Always-on connection.

Security risks:
- Broad network access
- Trust boundary expansion

---

## VPN Protocols (Security Relevant)

### IPsec
- Network-layer VPN
- Strong encryption
- Used for site-to-site and remote access

Components:
- IKE (key exchange)
- ESP (encryption)

---

### SSL/TLS VPN
- Uses TLS
- Runs over TCP 443
- Easily bypasses firewalls

Common in:
- Corporate VPN portals
- Browser-based VPNs

---

### OpenVPN
- Open-source
- Uses TLS
- Highly configurable

---

### WireGuard
- Modern VPN protocol
- Lightweight and fast
- Smaller attack surface

---

## VPN Authentication Methods
- Username and password
- Certificates
- Pre-shared keys
- Multi-factor authentication (MFA)

Lack of MFA is a major security risk.

---

## VPN Encryption
VPNs use:
- AES
- ChaCha20
- Secure hashing algorithms

Weak encryption breaks VPN security.

---

## VPN and Routing

### Full Tunnel
- All traffic goes through VPN.
- Higher security.
- Increased monitoring capability.

---

### Split Tunnel
- Only corporate traffic goes through VPN.
- Internet traffic bypasses VPN.

Security risk:
- Data leakage
- Attackers bypass inspection

---

## VPN Attacks

### Credential Theft
- Phishing VPN credentials.
- No MFA protection.

---

### VPN Exploits
- Vulnerabilities in VPN software.
- Examples: Fortinet, Pulse Secure, Ivanti.

---

### Split Tunnel Abuse
- Malware uses non-VPN route.
- Evades detection.

---

### VPN Pivoting
- Attacker uses VPN access to move laterally.
- Reaches internal systems.

---

## VPN Hardening Best Practices
- Enforce MFA.
- Disable split tunneling (where possible).
- Restrict VPN access by role.
- Patch VPN appliances.
- Monitor logs continuously.
- Use modern protocols (WireGuard, IPsec).

---

## VPN vs Zero Trust
VPN:
- Network-level trust.
- Broad access once connected.

Zero Trust:
- Identity-based access.
- Continuous verification.

Modern security is moving beyond VPN-only models.

---

## Key Cybersecurity Takeaway
VPN is a powerful security control and a potential attack vector. Proper configuration, robust authentication, and continuous monitoring are essential to secure remote access and prevent unauthorized intrusions.
