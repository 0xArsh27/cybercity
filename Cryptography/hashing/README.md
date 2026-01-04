# Hashing in Cybersecurity

Hashing is a fundamental cryptographic primitive used in cybersecurity to ensure data integrity, enable secure storage, and support authentication mechanisms. Unlike encryption, hashing is a one-way function that transforms input data into a fixed-size output (hash value) that cannot be reversed, making it ideal for verifying data without exposing the original content.

## Role in cybersecurity

- **Data integrity verification:** Hash functions detect accidental or malicious modifications to files, messages, or software. For example, checksums and digital signatures rely on hashing to confirm that data has not been altered.
- **Password storage:** Passwords are hashed (with salting) to prevent plaintext storage; during authentication, the hash of the entered password is compared to the stored hash.
- **Digital forensics and evidence integrity:** Hash values (e.g., MD5, SHA-256) are used to create digital fingerprints of evidence, ensuring chain-of-custody and tamper detection.
- **Secure communications:** Hashing supports message authentication codes (MACs) and HMAC for integrity in protocols like TLS and IPsec.
- **Blockchain and cryptocurrencies:** Hashing provides the basis for proof-of-work and immutable ledgers.

## Key concepts

- **One-way function:** Computationally infeasible to reverse the hash to recover the original input.
- **Collision resistance:** Difficult to find two different inputs that produce the same hash output.
- **Avalanche effect:** Small changes in input result in significantly different hash outputs.
- **Preimage resistance:** Hard to find an input that hashes to a specific output.

## Common hash algorithms

- **MD5:** Deprecated due to vulnerabilities (collisions found); avoid for security-critical applications.
- **SHA-1:** Weakened and phased out; no longer recommended for new systems.
- **SHA-256 (SHA-2 family):** Widely used for integrity checks, certificates, and blockchain.
- **SHA-3:** Modern alternative with strong security properties; suitable for high-assurance environments.
- **Blake2:** Fast and secure; gaining adoption for performance-sensitive use cases.

## Best practices

- **Use modern algorithms:** Prefer SHA-256 or higher; avoid MD5/SHA-1.
- **Salt passwords:** Always use unique salts with password hashing to prevent rainbow table attacks.
- **Key stretching:** Employ algorithms like PBKDF2, bcrypt, or Argon2 for password hashing to increase computational cost.
- **Combine with other primitives:** Hashing alone does not provide confidentiality; pair with encryption for comprehensive protection.
- **Monitor for weaknesses:** Stay updated on cryptanalysis; migrate algorithms as needed (crypto-agility).
- **Secure implementation:** Use vetted libraries; avoid custom hashing implementations.

## Operational considerations

- **Performance impact:** Hashing can be computationally intensive; choose algorithms based on resource constraints.
- **Length extension attacks:** Some hash functions (e.g., SHA-1) are vulnerable; use HMAC for authenticated hashing.
- **Quantum resistance:** Current hash functions are believed quantum-resistant, but monitor developments in post-quantum cryptography.

Explore the rest of this folder for practical guides on implementing hashing, password security, and integrity checks in real-world scenarios.
