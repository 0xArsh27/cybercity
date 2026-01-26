Performing a known-plaintext attack to recover a repeating-key XOR key and decrypt a hidden message.

Plaintext[i] = Ciphertext[i] XOR Key[i % key_length]


Repeating-key XOR is an encryption method where plaintext is XORed with a short key that repeats over the entire message.