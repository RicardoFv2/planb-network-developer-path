---
title: "Symmetric vs Asymmetric Cryptography"
description: "Understanding the difference between shared keys and public/private key pairs."
tags:
  - cryptography
  - security
  - math
---

# Symmetric vs Asymmetric Cryptography

> [!abstract] TL;DR
> Symmetric cryptography uses one shared key, while asymmetric cryptography uses a public/private key pair, enabling secure communication over public channels.

## Symmetric Cryptography

- **The Mechanism:** Information is encrypted and decrypted using the **same key**.
- **The Problem:** It requires a "secure channel" to exchange the key first. If an attacker intercepts the key, they can read all future messages.
- **Example:** A physical safe with one key.

## Asymmetric (Public Key) Cryptography

- **The Mechanism:** Uses a mathematically linked pair of keys.
  - **Public Key:** Can be shared with anyone (like an email address).
  - **Private Key:** Must be kept secret (like a password).
- **Function:** Anything encrypted with the public key can **only** be decrypted by the private key.
- **Analogy:** A public mailbox. Anyone can drop a letter in (encrypt), but only the owner has the key to open it and read the contents (decrypt).

## Why This Matters for Bitcoin

Bitcoin relies entirely on **Asymmetric Cryptography** (ECDSA). Your "wallet" is a collection of private keys. Your "address" is derived from your public key. This allows you to receive funds from anyone in the world without having to share your secret private key.

## Related Notes

- [[Digital-Signatures-and-Authorship]]
- [[Hash-Functions-and-Pre-image-Resistance]]
- [[Blind-Signatures-for-Privacy]]

#cryptography #security #math #encryption
