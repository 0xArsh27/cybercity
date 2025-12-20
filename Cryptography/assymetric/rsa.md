================
RSA ALGORITHM 
================

RSA (Rivest–Shamir–Adleman) is an asymmetric cryptographic algorithm used for secure data transmission, authentication, and digital signatures. It is based on the mathematical difficulty of factoring large prime numbers.

-------------------------------------
WHAT TYPE OF CRYPTOGRAPHY IS RSA?
-------------------------------------
- Asymmetric (Public Key Cryptography)
- Uses two keys:
  1. Public Key – shared openly
  2. Private Key – kept secret

What is encrypted with one key can only be decrypted with the other.

-------------------------------------
WHY RSA IS IMPORTANT
-------------------------------------
- Secure key exchange
- Digital certificates (HTTPS)
- Authentication
- Digital signatures
- PKI infrastructure

RSA DOES NOT encrypt large data directly.
It is mainly used to:
- Exchange symmetric keys
- Sign data

-------------------------------------
RSA KEY GENERATION (CORE CONCEPT)
-------------------------------------
1. Choose two large prime numbers:
   p and q

2. Compute:
   n = p × q
   (n is part of both public and private keys)

3. Compute Euler’s Totient:
   φ(n) = (p − 1)(q − 1)

4. Choose public exponent e:
   - 1 < e < φ(n)
   - gcd(e, φ(n)) = 1
   - Common value: 65537

5. Compute private exponent d:
   d ≡ e⁻¹ mod φ(n)

Public Key  = (e, n)
Private Key = (d, n)

Security of RSA depends on keeping p, q, and d secret.

-------------------------------------
RSA ENCRYPTION PROCESS
-------------------------------------
Encryption is done using the RECEIVER’S public key.

Formula:
Ciphertext C = M^e mod n

Where:
- M = message
- e = public exponent
- n = modulus

Only the receiver can decrypt the message using the private key.

-------------------------------------
RSA DECRYPTION PROCESS
-------------------------------------
Decryption is done using the PRIVATE key.

Formula:
Message M = C^d mod n

Where:
- d = private exponent

This ensures confidentiality.

-------------------------------------
RSA FOR DIGITAL SIGNATURES
-------------------------------------
RSA can also be used for authentication and non-repudiation.

Signing Process:
1. Sender hashes the message
2. Hash is encrypted using sender’s PRIVATE key
3. This encrypted hash is the digital signature

Verification Process:
1. Receiver decrypts signature using sender’s PUBLIC key
2. Receiver hashes the message again
3. Both hashes are compared

If they match:
- Sender is verified
- Message integrity is intact

-------------------------------------
RSA IN TLS / HTTPS
-------------------------------------
RSA is used during the TLS handshake to:
- Exchange symmetric session keys securely
- Authenticate the server using certificates

After handshake:
- Symmetric encryption (AES) is used for data transfer
(RSA is too slow for bulk data)

-------------------------------------
RSA KEY SIZES
-------------------------------------
Common RSA key sizes:
- 1024-bit – insecure (deprecated)
- 2048-bit – minimum recommended
- 3072-bit – stronger security
- 4096-bit – high security, slower

Larger key = stronger security but slower performance.

-------------------------------------
RSA STRENGTHS
-------------------------------------
- Strong mathematical foundation
- Widely supported
- Trusted for decades
- Essential for PKI and certificates

-------------------------------------
RSA WEAKNESSES
-------------------------------------
- Slow compared to symmetric encryption
- Vulnerable if small keys are used
- Susceptible to poor random number generation
- Quantum computing threatens RSA in the future

-------------------------------------
COMMON RSA ATTACKS
-------------------------------------
- Brute-force factorization (small keys)
- Man-in-the-Middle (if certificates not verified)
- Padding oracle attacks
- Poor key management
- Weak random primes

-------------------------------------
RSA VS AES (REALITY CHECK)
-------------------------------------
RSA:
- Asymmetric
- Slow
- Used for key exchange and signatures

AES:
- Symmetric
- Fast
- Used for encrypting actual data

That is why modern systems use BOTH.

-------------------------------------
RSA IN REAL CYBERSECURITY ROLES
-------------------------------------
SOC Analyst:
- Analyze TLS certificates
- Detect weak RSA key usage

DFIR:
- Verify signed files
- Validate certificate chains

Blue Team:
- Enforce key length policies
- Monitor encryption standards

Red Team:
- Exploit weak RSA implementations

-------------------------------------
RSA MINDSET (VERY IMPORTANT)
-------------------------------------
RSA does not protect data by itself.
RSA protects the keys that protect the data.

If RSA is broken → trust is broken.
If trust is broken → security collapses.


