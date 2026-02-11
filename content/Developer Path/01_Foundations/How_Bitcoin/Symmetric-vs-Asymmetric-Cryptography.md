# Symmetric vs. Asymmetric Cryptography

## Symmetric Cryptography
- **Mechanism:** Uses a single shared secret key for both encryption and decryption.
- **Example:** The **Caesar Cipher** (shifting letters by a fixed number $n$).
- **The "Secure Channel" Problem:** Both parties must meet in person or use a secure way to exchange the key before they can communicate. This does not scale for the internet.
- **Vulnerability:** If the key is intercepted, all communication is compromised.

## Asymmetric (Public-Key) Cryptography
- **Mechanism:** Uses a **Key Pair**—one Public and one Private.
    - **Public Key:** Shared openly. Used by others to encrypt messages for you.
    - **Private Key:** Kept secret. Used only by you to decrypt those messages.
- **Analogy:** A public mailbox where anyone can drop a letter (encryption with public key), but only the owner has the key to open it (decryption with private key).
- **The Breakthrough:** It eliminates the need for a "secure channel" to exchange keys. You can communicate securely with complete strangers.

## Role in Bitcoin
Bitcoin uses asymmetric cryptography (specifically **Elliptic Curve Cryptography**) to define ownership. Your "Bitcoin Address" is derived from your Public Key, and your ability to spend is controlled by your Private Key.

---
#bitcoin #cryptography #security
