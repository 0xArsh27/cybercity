=====================================
PGP & GPG – CYBERSECURITY NOTES
=====================================

PGP (Pretty Good Privacy) and GPG (GNU Privacy Guard) are cryptographic systems used to secure communication and data using encryption, digital signatures, and key management. They are commonly used for secure email, file encryption, and identity verification.

-------------------------------------
WHAT IS PGP?
-------------------------------------
PGP (Pretty Good Privacy) is a cryptographic protocol designed to provide:
- Confidentiality
- Integrity
- Authentication
- Non-repudiation

PGP uses a combination of:
- Symmetric encryption
- Asymmetric encryption
- Hashing
- Digital signatures

This combination makes PGP a HYBRID cryptographic system.

-------------------------------------
WHAT IS GPG?
-------------------------------------
GPG (GNU Privacy Guard) is an open-source implementation of the PGP standard.

Key points:
- Free and open-source
- Command-line based
- Widely used in Linux
- Compatible with PGP

In practice:
PGP = concept / standard
GPG = tool / implementation

-------------------------------------
WHY PGP / GPG IS IMPORTANT
-------------------------------------
- Secure email communication
- Secure file storage and sharing
- Identity verification
- Software package signing
- Used in Linux repositories and Git commits

-------------------------------------
CRYPTOGRAPHY USED IN PGP / GPG
-------------------------------------
- Symmetric encryption (AES)
- Asymmetric encryption (RSA, ECC)
- Hashing (SHA-256)
- Digital signatures

-------------------------------------
PGP ENCRYPTION PROCESS (SIMPLIFIED)
-------------------------------------
1. Sender writes a message
2. Message is compressed
3. Message is hashed
4. A random symmetric session key is generated
5. Message is encrypted using the session key (AES)
6. Session key is encrypted using receiver’s PUBLIC key
7. Encrypted message + encrypted session key are sent

Only the receiver can decrypt the session key using their PRIVATE key.

-------------------------------------
PGP DECRYPTION PROCESS
-------------------------------------
1. Receiver decrypts session key using PRIVATE key
2. Session key decrypts the message
3. Message is decompressed and read

-------------------------------------
DIGITAL SIGNATURES IN PGP
-------------------------------------
PGP supports message signing to ensure authenticity.

Signing Process:
1. Sender hashes the message
2. Hash is encrypted using sender’s PRIVATE key
3. Digital signature is attached to the message

Verification Process:
1. Receiver decrypts signature using sender’s PUBLIC key
2. Hash is recalculated
3. Hashes are compared

-------------------------------------
KEY CONCEPT: WEB OF TRUST
-------------------------------------
PGP does NOT rely on centralized Certificate Authorities.

Instead, it uses a Web of Trust:
- Users sign each other’s public keys
- Trust is built socially
- Trust increases as more people verify a key

This is different from PKI (CA-based trust).

-------------------------------------
PGP VS PKI (CERTIFICATE AUTHORITY)
-------------------------------------
PGP:
- Decentralized trust
- User-to-user verification
- Web of Trust model

PKI:
- Centralized trust
- Certificate Authorities
- Used in HTTPS and enterprise systems

-------------------------------------
GPG KEY GENERATION
-------------------------------------
Generate a key pair:
gpg --full-generate-key

What it creates:
- Public key (shareable)
- Private key (secret)

Keys are stored in:
~/.gnupg/

-------------------------------------
COMMON GPG COMMANDS (IMPORTANT)
-------------------------------------
List keys:
gpg --list-keys

Export public key:
gpg --export -a username > publickey.asc

Import public key:
gpg --import publickey.asc

Encrypt a file:
gpg -e -r username file.txt

Decrypt a file:
gpg -d file.txt.gpg

Sign a file:
gpg --sign file.txt

Verify a signature:
gpg --verify file.txt.gpg

-------------------------------------
PGP / GPG IN REAL CYBERSECURITY
-------------------------------------
SOC Analyst:
- Verify signed packages
- Detect tampered files

DFIR:
- Validate file authenticity
- Verify malware signatures

Blue Team:
- Secure internal communication
- Enforce file signing

Red Team:
- Abuse trust relationships
- Hide payloads using encryption

-------------------------------------
COMMON ATTACKS & RISKS
-------------------------------------
- Compromised private keys
- Weak passphrases
- Trusting unverified public keys
- Social engineering in Web of Trust

-------------------------------------
BEST PRACTICES
-------------------------------------
- Protect private keys with strong passphrases
- Verify public keys before trusting
- Rotate keys periodically
- Revoke keys if compromised
- Backup private keys securely

-------------------------------------
PGP / GPG VS TLS
-------------------------------------
PGP/GPG:
- End-to-end encryption
- User-controlled keys
- Email and file security

TLS:
- Transport-level encryption
- CA-based trust
- Web communication

-------------------------------------
SECURITY MINDSET
-------------------------------------
Encryption protects data.
Digital signatures protect authenticity.
Trust determines security.

If trust is misplaced → encryption is meaningless.

=====================================
END OF PGP & GPG NOTES
=====================================
