# TLS (Transport Layer Security) – Cybersecurity Focused Notes

## What is TLS
TLS (Transport Layer Security) is a cryptographic protocol that provides secure communication over a network. TLS ensures confidentiality, integrity, and authentication between communicating parties.

TLS is the successor to SSL (Secure Sockets Layer).
SSL is deprecated and insecure.

TLS is commonly used in:
- HTTPS
- SMTP with STARTTLS
- FTPS
- VPNs
- Secure APIs

---

## Why TLS is Critical in Cybersecurity
TLS protects:
- Credentials
- Sensitive data
- Session cookies
- API tokens

Without TLS, attackers can:
- Sniff traffic
- Steal credentials
- Modify data
- Perform Man-in-the-Middle (MITM) attacks

---

## What TLS Provides (CIA Triad)

### Confidentiality
- Data is encrypted
- Prevents packet sniffing

### Integrity
- Detects data tampering
- Prevents silent modification

### Authentication
- Verifies server identity
- Prevents impersonation

---

## TLS vs SSL
SSL:
- Old and insecure
- Vulnerable to multiple attacks

TLS:
- Secure replacement
- Actively maintained
- Industry standard

Modern systems must use TLS 1.2 or TLS 1.3.

---

## TLS Handshake (VERY IMPORTANT)
The TLS handshake establishes a secure session.

Simplified flow:
1. ClientHello (supported ciphers, TLS version)
2. ServerHello (chosen cipher, certificate)
3. Certificate verification
4. Key exchange
5. Secure session established

Handshake is a prime target for attackers.

---

## TLS Versions (Security Relevant)

- TLS 1.0 → Insecure
- TLS 1.1 → Insecure
- TLS 1.2 → Secure (widely used)
- TLS 1.3 → Most secure, faster handshake

TLS 1.0 and 1.1 should be disabled.

---

## Certificates and PKI

### Digital Certificates
Certificates bind:
- Domain name
- Public key
- Organization identity

Issued by:
- Certificate Authorities (CAs)

---

### Certificate Authority (CA)
Trusted third party that:
- Verifies identity
- Issues certificates

If a CA is compromised, trust collapses.

---

## Certificate Chain of Trust
- Root CA
- Intermediate CA
- Server certificate

Browsers validate the entire chain.

---

## TLS Cipher Suites
A cipher suite defines:
- Key exchange algorithm
- Encryption algorithm
- Integrity algorithm

Weak ciphers = broken TLS.

Examples:
- AES-GCM (secure)
- RC4 (insecure)
- 3DES (deprecated)

---

## TLS and HTTPS
HTTPS = HTTP + TLS

TLS secures:
- URLs
- Headers
- Cookies
- Request/response bodies

TLS does NOT fix:
- SQL injection
- XSS
- Logic flaws

---

## TLS Attacks (VERY IMPORTANT)

### Man-in-the-Middle (MITM)
- Attacker intercepts traffic
- Presents fake certificate
- Works if users ignore warnings

---

### SSL Stripping
- Downgrades HTTPS to HTTP
- Steals credentials
- Prevented by HSTS

---

### Downgrade Attacks
- Force weak TLS versions
- Exploit legacy support

---

### Weak Certificate Validation
- Expired certificates
- Self-signed certificates
- Incorrect hostname validation

---

## TLS and Malware
Malware uses TLS to:
- Hide C2 communication
- Evade IDS/IPS
- Blend with normal traffic

Encrypted traffic ≠ safe traffic.

---

## TLS Inspection (Defensive Security)
Organizations may:
- Decrypt TLS traffic
- Inspect payloads
- Re-encrypt traffic

Security tradeoff:
- Visibility vs privacy

---

## TLS in SOC & Incident Response
SOC teams analyze:
- TLS handshake metadata
- Certificate anomalies
- JA3/JA4 fingerprints
- Unusual encrypted traffic patterns

TLS metadata is crucial when payloads are encrypted.

---

## TLS in Packet Analysis
In Wireshark:
- Filter: `tls`
- Payload encrypted
- Handshake visible

Red flags:
- Old TLS versions
- Weak cipher suites
- Suspicious certificates

---

## TLS and DNS
TLS relies on DNS:
- Domain name resolution
- Certificate hostname validation

DNS poisoning can assist TLS MITM attacks.

---

## TLS and Email Security
Used in:
- SMTP STARTTLS
- IMAP over TLS
- POP3 over TLS

Misconfigured TLS enables:
- Credential theft
- Email interception

---

## TLS Hardening Best Practices
- Enforce TLS 1.2 or 1.3
- Disable weak ciphers
- Enable HSTS
- Use trusted CAs
- Monitor certificate expiry
- Implement certificate transparency

---

## TLS vs VPN Encryption
TLS:
- Application-level encryption
- Protects specific services

VPN:
- Network-level encryption
- Protects all traffic

Both rely on strong cryptography.

---

## Key Cybersecurity Takeaway
TLS is the foundation of trust on the internet.

Mastering TLS allows you to:
- Detect MITM attacks
- Analyze encrypted traffic
- Secure web and email services
- Understand malware evasion
- Perform advanced SOC investigations
