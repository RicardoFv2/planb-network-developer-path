---
title: "Digital Signatures and Authorship"
description: "Ensuring authenticity and non-repudiation in digital transactions."
tags:
  - cryptography
  - signatures
  - security
---

[[index|← Return to Index]]

# Digital Signatures and Authorship

> [!abstract] TL;DR
> Digital signatures prove that a message was created by a specific sender and has not been altered, providing "unforgeable authorship."

## What Is It?

A digital signature is a mathematical scheme for verifying the authenticity of digital messages or documents. It uses **Asymmetric Cryptography**:

- **Private Key:** Used to "sign" the message. Only the owner knows it.
- **Public Key:** Used by anyone to "verify" that the signature matches the message and the private key.

## Why Does It Matter?

In Bitcoin, digital signatures are used to prove ownership of coins. When you send bitcoin, you are signing a message that says: "I, the owner of this public key, authorize the transfer of these funds to a new public key." Without digital signatures, anyone could pretend to be you and spend your money (Identity Theft).

## Key Properties

- **Authenticity:** You know who sent it.
- **Non-repudiation:** The sender cannot deny signing it later.
- **Integrity:** If even one bit of the message changes, the signature becomes invalid.

## Related Notes

- [[Symmetric-vs-Asymmetric-Cryptography]]
- [[Hash-Functions-and-Pre-image-Resistance]]
- [[Blind-Signatures-for-Privacy]]
#cryptography #signatures #security #identity

[[index|← Return to Index]]
