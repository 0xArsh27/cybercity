========================================
DIFFIE–HELLMAN & KEY EXCHANGE – NOTES
========================================

Diffie–Hellman (DH) is a cryptographic key exchange algorithm that allows two parties to securely generate a shared secret key over an insecure network without ever transmitting the key itself.

----------------------------------------
WHY KEY EXCHANGE IS REQUIRED
----------------------------------------
Symmetric encryption is fast and secure, but it has a major problem:
How do two parties securely share the secret key over the internet?

Diffie–Hellman solves this problem.

----------------------------------------
TYPE OF CRYPTOGRAPHY
----------------------------------------
- Asymmetric cryptography (used for key exchange)
- NOT used for encrypting data
- Used ONLY to generate a shared secret

----------------------------------------
CORE IDEA OF DIFFIE–HELLMAN
----------------------------------------
Two parties can:
- Agree on public values
- Independently compute the same secret key
- Never send the secret key over the network

Even if an attacker listens to everything, the secret remains safe.

----------------------------------------
DIFFIE–HELLMAN TERMINOLOGY
----------------------------------------
p → Large prime number (public)
g → Generator (public)
a → Private key of Alice (secret)
b → Private key of Bob (secret)

----------------------------------------
DIFFIE–HELLMAN KEY EXCHANGE PROCESS
----------------------------------------
1. Alice and Bob agree on:
   - Prime number p
   - Generator g
   (Both are public)

2. Alice chooses a private value a
   Alice computes:
   A = g^a mod p
   Alice sends A to Bob

3. Bob chooses a private value b
   Bob computes:
   B = g^b mod p
   Bob sends B to Alice

4. Alice computes shared secret:
   S = B^a mod p

5. Bob computes shared secret:
   S = A^b mod p

Result:
Both Alice and Bob now have the SAME shared secret key.

----------------------------------------
WHY DIFFIE–HELLMAN IS SECURE
----------------------------------------
An attacker can see:
- p
- g
- A
- B

But cannot compute:
- a or b
- shared secret S

This is because of the Discrete Logarithm Problem, which is computationally infeasible for large values.

----------------------------------------
DIFFIE–HELLMAN IN REAL SYSTEMS
----------------------------------------
Used in:
- TLS / HTTPS
- VPNs (IPSec, OpenVPN)
- SSH
- Secure messaging apps

After DH:
- A symmetric key (AES) is used for data encryption

----------------------------------------
EPHEMERAL DIFFIE–HELLMAN (DHE)
----------------------------------------
DHE uses temporary (ephemeral) keys for each session.

Benefits:
- Perfect Forward Secrecy (PFS)
- Even if long-term keys are compromised, past sessions remain secure

----------------------------------------
ELLIPTIC CURVE DIFFIE–HELLMAN (ECDH)
----------------------------------------
ECDH is a modern, efficient version of DH.

Advantages:
- Smaller key sizes
- Faster performance
- Stronger security per bit

Common usage:
- TLS 1.2 / TLS 1.3
- Mobile and cloud environments

----------------------------------------
DIFFIE–HELLMAN VS RSA (KEY EXCHANGE)
----------------------------------------
Diffie–Hellman:
- No key is transmitted
- Provides Perfect Forward Secrecy
- Preferred in modern TLS

RSA:
- Encrypts symmetric key directly
- No forward secrecy (traditional RSA)
- Being phased out for key exchange

----------------------------------------
MAN-IN-THE-MIDDLE (MITM) RISK
----------------------------------------
Basic Diffie–Hellman is vulnerable to MITM if authentication is missing.

Solution:
- Use certificates
- Use authenticated Diffie–Hellman (TLS + PKI)

----------------------------------------
COMMON DIFFIE–HELLMAN ATTACKS
----------------------------------------
- Man-in-the-Middle (unauthenticated DH)
- Weak prime numbers
- Small key sizes
- Logjam attack (weak DH groups)

----------------------------------------
KEY SIZES (RECOMMENDED)
----------------------------------------
- DH: 2048 bits minimum
- ECDH: 256 bits or higher

----------------------------------------
WHY SOC / DFIR MUST UNDERSTAND DH
----------------------------------------
SOC Analyst:
- Analyze TLS handshakes
- Detect weak DH groups

DFIR:
- Understand encrypted traffic behavior
- Identify downgrade attacks

Blue Team:
- Enforce strong cipher suites
- Disable weak DH configurations

Red Team:
- Exploit weak or misconfigured key exchange

----------------------------------------
DIFFIE–HELLMAN MINDSET
----------------------------------------
Encryption protects data.
Diffie–Hellman protects the encryption key.

If key exchange is weak → encryption is useless.
Secure key exchange is the foundation of secure communication.

