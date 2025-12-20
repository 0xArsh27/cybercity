==================================================
DIGITAL SIGNATURES & DIGITAL CERTIFICATES – NOTES
==================================================

Digital signatures and digital certificates are the foundation of trust on the internet. They ensure authentication, integrity, and non-repudiation in secure communications such as HTTPS, software updates, email security, and VPNs.

--------------------------------------------------
DIGITAL SIGNATURES – OVERVIEW
--------------------------------------------------
A digital signature is a cryptographic mechanism used to verify:
- Who sent the data (authentication)
- Whether the data was altered (integrity)
- That the sender cannot deny sending it (non-repudiation)

Digital signatures do NOT encrypt the data.
They protect trust and integrity.

--------------------------------------------------
CRYPTOGRAPHY USED IN DIGITAL SIGNATURES
--------------------------------------------------
- Hashing (SHA-256, SHA-512)
- Asymmetric cryptography (RSA, ECDSA)

--------------------------------------------------
DIGITAL SIGNATURE CREATION PROCESS
--------------------------------------------------
1. Sender creates a hash of the message
2. Hash is encrypted using sender’s PRIVATE key
3. The encrypted hash becomes the digital signature
4. Message + signature are sent to receiver

--------------------------------------------------
DIGITAL SIGNATURE VERIFICATION PROCESS
--------------------------------------------------
1. Receiver decrypts signature using sender’s PUBLIC key
2. Receiver hashes the received message
3. Both hash values are compared

If hashes match:
- Message is authentic
- Message integrity is verified
- Sender is confirmed

--------------------------------------------------
WHERE DIGITAL SIGNATURES ARE USED
--------------------------------------------------
- HTTPS communication
- Software and OS updates
- Secure emails
- Code signing
- Blockchain transactions

--------------------------------------------------
DIGITAL CERTIFICATES – OVERVIEW
--------------------------------------------------
A digital certificate is an electronic document that binds:
- An identity (website, organization, person)
- To a public key

Certificates solve the problem:
“How do we trust a public key?”

--------------------------------------------------
WHAT A DIGITAL CERTIFICATE CONTAINS
--------------------------------------------------
- Subject name (domain or entity)
- Public key
- Certificate Authority (CA) name
- Validity period
- Serial number
- Digital signature of the CA
- Encryption and hashing algorithms used

--------------------------------------------------
CERTIFICATE AUTHORITY (CA)
--------------------------------------------------
A Certificate Authority is a trusted third party that:
- Verifies identities
- Issues digital certificates
- Digitally signs certificates

Examples:
- Root CA
- Intermediate CA

--------------------------------------------------
PUBLIC KEY INFRASTRUCTURE (PKI)
--------------------------------------------------
PKI is the system that manages:
- Certificate creation
- Certificate validation
- Certificate revocation
- Trust relationships

Key PKI Components:
- Root CA
- Intermediate CA
- End-entity certificate
- Certificate Revocation List (CRL)
- OCSP (Online Certificate Status Protocol)

--------------------------------------------------
CERTIFICATE CHAIN OF TRUST
--------------------------------------------------
1. Server presents its certificate
2. Browser checks Intermediate CA
3. Browser verifies Root CA
4. Root CA is trusted by OS/browser

If chain is valid → connection is trusted
If chain fails → security warning appears

--------------------------------------------------
DIGITAL CERTIFICATES IN HTTPS (TLS)
--------------------------------------------------
During TLS handshake:
1. Server sends its digital certificate
2. Client verifies certificate signature
3. Client checks:
   - Domain name match
   - Expiry date
   - Revocation status
4. Secure key exchange begins

Certificates authenticate the SERVER.
Encryption protects the DATA.

--------------------------------------------------
TYPES OF DIGITAL CERTIFICATES
--------------------------------------------------
1. Domain Validation (DV)
   - Confirms domain ownership
   - Fast, basic trust

2. Organization Validation (OV)
   - Confirms organization identity
   - Medium trust

3. Extended Validation (EV)
   - Strict identity verification
   - Highest trust level

--------------------------------------------------
CERTIFICATE REVOCATION
--------------------------------------------------
Certificates can be revoked if:
- Private key is compromised
- Certificate issued incorrectly
- Organization is no longer valid

Revocation Methods:
- CRL
- OCSP

--------------------------------------------------
COMMON CERTIFICATE ERRORS
--------------------------------------------------
- Expired certificate
- Self-signed certificate
- Domain mismatch
- Untrusted CA
- Revoked certificate

--------------------------------------------------
DIGITAL SIGNATURES VS CERTIFICATES
--------------------------------------------------
Digital Signature:
- Verifies data integrity & sender
- Uses private key
- Protects messages

Digital Certificate:
- Verifies identity
- Binds public key to entity
- Issued by trusted CA

--------------------------------------------------
ROLE IN CYBERSECURITY (SOC / DFIR)
--------------------------------------------------
SOC Analyst:
- Detect certificate anomalies
- Identify MITM attacks
- Monitor invalid TLS handshakes

DFIR:
- Verify signed files
- Validate certificate chains
- Analyze malicious certificates

Blue Team:
- Enforce certificate policies
- Monitor expiry & revocation
- Harden TLS configurations

Red Team:
- Exploit weak certificates
- Abuse misconfigured PKI
- Perform MITM attacks

--------------------------------------------------
COMMON ATTACKS RELATED TO CERTIFICATES
--------------------------------------------------
- Man-in-the-Middle attacks
- Fake certificates
- Compromised CAs
- Weak signature algorithms
- Certificate spoofing

--------------------------------------------------
SECURITY MINDSET
--------------------------------------------------
Encryption protects secrecy.
Digital signatures protect integrity.
Certificates protect trust.
