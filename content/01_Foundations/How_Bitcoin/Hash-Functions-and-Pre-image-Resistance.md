---
title: "Hash Functions and Pre-image Resistance"
description: "The mathematical 'one-way' functions that secure Bitcoin's data."
tags:
  - cryptography
  - math
  - security
---

# Hash Functions and Pre-image Resistance

> [!abstract] TL;DR
> A hash function is a one-way mathematical function that turns any input into a fixed-length fingerprint, essential for Bitcoin's security.

## What Is It?

A cryptographic hash function (like SHA-256 used in Bitcoin) has several critical properties:

1.  **Deterministic:** The same input always produces the same output.
2.  **Fast:** It's cheap to calculate the hash.
3.  **Pre-image Resistant (One-Way):** Given a hash, it is impossible to figure out what the original input was.
4.  **Collision Resistant:** Two different inputs should never produce the same hash.
5.  **Avalanche Effect:** Changing even one bit of the input changes the entire resulting hash completely.

## Why Does It Matter?

Hash functions are the "glue" of Bitcoin:

- **Mining:** Proof of Work is the search for a specific hash.
- **Addresses:** Your Bitcoin address is a hash of your public key.
- **Immutability:** Each block contains the hash of the previous block. If you change a single transaction in history, all subsequent hashes break.

## Analogy: The Fingerprint

A hash is like a **fingerprint**. You can't reconstruct a human being from their fingerprint, but you can use the fingerprint to instantly verify that "this person" matches "this record."

## Related Notes

- [[Merkle-Trees-and-Timestamping]]
- [[Proof-of-Work-Unforgeable-Costliness]]
- [[Digital-Signatures-and-Authorship]]

#cryptography #math #security #hashing
