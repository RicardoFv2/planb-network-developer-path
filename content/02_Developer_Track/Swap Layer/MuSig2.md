---
title: "MuSig2 & Schnorr Signatures"
description: "The cryptographic upgrade allowing scalable, hidden multi-signature schemes on Bitcoin."
tags:
  - developer-track
  - taproot
  - schnorr
  - cryptography
---

# MuSig2 & Schnorr Signatures

[[02_Developer_Track/index-MOC#lecture-02|← Return to Index]]

> [!abstract] TL;DR
> MuSig2 is a multi-signature scheme for Schnorr signatures that allows multiple parties to create a single aggregated public key and signature, improving privacy and efficiency.

## The Shift from ECDSA to Schnorr
Historically, Bitcoin used the Elliptic Curve Digital Signature Algorithm (ECDSA) because Klaus Schnorr held a patent on his more efficient signature algorithm until 2008. 
With the Taproot upgrade, Bitcoin integrated Schnorr signatures. Unlike ECDSA, Schnorr signatures are mathematically simpler and exhibit a property called **linearity**.

## How MuSig2 Works
Because of this linearity, MuSig2 allows multiple independent parties to collaboratively mask their participation behind what looks like a single signature.
1. **Key Aggregation:** Alice, Bob, and Carol take their individual public keys and combine them off-chain into one "Aggregated Public Key."
2. **Signing:** When they wish to spend, they communicate off-chain to each produce a partial signature.
3. **Signature Aggregation:** These partial signatures are computationally added together into one final, valid Schnorr signature.

## Impact on Swaps and Smart Contracts
In the context of Submarine Swaps, the swap provider and the user use MuSig2 to aggregate their keys.
- **Privacy:** To the blockchain, the multi-party contract looks exactly like a normal, single-person Bitcoin transaction (a "Key Path Spend"). No one can tell a submarine swap took place.
- **Efficiency:** Instead of paying for 2 or 3 signatures in block space, they only pay for 1. This significantly reduces fees for complex, multi-party smart contracts.

---

**References:**
- [[02_Developer_Track/02. Technical Part (Swaps & Layers) - Deep Dive Summary|02. Technical Part (Swaps & Layers) - Deep Dive Summary]]
