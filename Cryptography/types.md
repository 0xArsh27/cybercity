=====================================
TYPES OF CRYPTOGRAPHY – CYBERSECURITY NOTES
=====================================

Cryptography can be classified into different types based on how keys are used and what security goal is achieved. Each type plays a critical role in modern cybersecurity systems.

-------------------------------------
1. SYMMETRIC KEY CRYPTOGRAPHY
-------------------------------------
Symmetric cryptography uses the SAME key for both encryption and decryption.

Plaintext + Secret Key  → Encryption → Ciphertext
Ciphertext + Same Key   → Decryption → Plaintext

Key Characteristics:
- Fast and efficient
- Suitable for large amounts of data
- Key distribution is the biggest challenge

Common Algorithms:
- AES (Advanced Encryption Standard) – most widely used
- DES – obsolete (insecure)
- 3DES – legacy, slow

Where Used:
- Disk encryption (BitLocker, FileVault)
- Database encryption
- VPN tunnels
- TLS data transmission (after handshake)

Advantages:
- High speed
- Low computational cost

Disadvantages:
- Secure key sharing problem
- Not scalable for large networks

-------------------------------------
2. ASYMMETRIC KEY CRYPTOGRAPHY
-------------------------------------
Asymmetric cryptography uses TWO keys:
- Public Key (shared)
- Private Key (secret)

What one key encrypts, only the other can decrypt.

Encryption Flow:
Plaintext + Receiver Public Key → Ciphertext
Ciphertext + Receiver Private Key → Plaintext

Key Characteristics:
- Slower than symmetric encryption
- Solves key distribution problem
- Provides authentication and non-repudiation

Common Algorithms:
- RSA
- ECC (Elliptic Curve Cryptography)
- Diffie-Hellman (key exchange)

Where Used:
- TLS/SSL handshake
- Digital certificates
- Secure email
- Key exchange mechanisms

Advantages:
- Secure key exchange
- Enables authentication

Disadvantages:
- Slower performance
- Computationally expensive

-------------------------------------
3. HASHING (ONE-WAY CRYPTOGRAPHY)
-------------------------------------
Hashing converts data into a fixed-length value using a mathematical function.
It is ONE-WAY and cannot be reversed.

Plaintext → Hash Function → Hash Value

Key Characteristics:
- One-way only (no decryption)
- Fixed output size
- Extremely sensitive to input change

Common Algorithms:
- MD5 – broken
- SHA-1 – broken
- SHA-256 – secure
- SHA-512 – secure

Where Used:
- Password storage
- File integrity checking
- Digital signatures
- Blockchain

Important Concept:
Even a single character change results in a completely different hash.

-------------------------------------
4. DIGITAL SIGNATURES
-------------------------------------
Digital signatures provide:
- Authentication
- Integrity
- Non-repudiation

How It Works:
1. Sender hashes the message
2. Hash is encrypted with sender’s PRIVATE key
3. Receiver decrypts using sender’s PUBLIC key
4. Hashes are compared for verification

Key Characteristics:
- Uses both hashing and asymmetric cryptography
- Confirms sender identity
- Ensures message was not modified

Where Used:
- Software updates
- Secure emails
- Certificates
- Blockchain transactions

-------------------------------------
5. KEY EXCHANGE CRYPTOGRAPHY
-------------------------------------
Key exchange methods securely share symmetric keys over insecure networks.

Common Methods:
- Diffie-Hellman
- Elliptic Curve Diffie-Hellman (ECDH)

Purpose:
- Establish a shared secret
- Prevent eavesdropping
- Used before symmetric encryption starts

Where Used:
- TLS handshake
- VPN tunnels
- Secure messaging apps

-------------------------------------
6. HYBRID CRYPTOGRAPHY
-------------------------------------
Hybrid cryptography combines multiple cryptographic types.

How It Works:
- Asymmetric cryptography for key exchange
- Symmetric cryptography for data encryption
- Hashing for integrity

Best Example:
HTTPS (TLS)

Advantages:
- Secure
- Fast
- Scalable
- Industry standard

-------------------------------------
COMPARISON SUMMARY
-------------------------------------
Symmetric  → Fast, same key, data encryption
Asymmetric → Secure key exchange, authentication
Hashing    → Integrity, password security
Digital Signature → Authentication + integrity
Hybrid     → Real-world secure systems

-------------------------------------
WHY THIS MATTERS IN CYBERSECURITY
-------------------------------------
- SOC analysts analyze encrypted traffic
- DFIR teams verify file integrity
- Blue teams validate certificates
- Red teams exploit weak crypto
- Blockchain security relies on hashes & signatures

-------------------------------------
CRYPTOGRAPHY SECURITY MINDSET
-------------------------------------
If encryption is weak → data leaks
If hashing is weak → passwords crack
If certificates fail → trust collapses
Cryptography is the backbone of cybersecurity


