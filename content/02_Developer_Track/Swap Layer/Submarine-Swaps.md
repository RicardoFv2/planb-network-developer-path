---
title: "Submarine Swaps"
description: "Trustless interoperability between on-chain Bitcoin and the off-chain Lightning Network."
tags:
  - developer-track
  - submarine-swaps
  - lightning-network
  - boltz
---

# Submarine Swaps

[[02_Developer_Track/index-MOC#lecture-02|← Return to Index]]

> [!abstract] TL;DR
> Submarine Swaps enable trustless atomic exchanges between on-chain Bitcoin and off-chain layers like Lightning by utilizing the atomicity of HTLCs.

> [!abstract] Core Concept
> A Submarine Swap is an atomic protocol that bridges Lightning Network liquidity with on-chain Bitcoin liquidity. Utilizing Hash Time Locked Contracts (HTLCs), they eliminate counterparty risk and permit continuous flow of capital across the protocol divide.

## Normal Swap (On-Chain to LN)
A scenario where a user has on-chain funds and wants them converted to Lightning funds (perhaps to pay an invoice or gain inbound liquidity).
1. **The Setup:** The user generates a Lightning invoice.
2. **The Lock:** The user creates an on-chain HTLC, locking the funds under the hash of the invoice's secret, plus a fallback timeout.
3. **The Swap:** A Swap Provider (like Boltz) observes the on-chain lock, safely pays the Lightning invoice (acquiring the secret preimage acting as proof-of-payment), and turns around to sweep the on-chain HTLC using that newly acquired secret.

## Reverse Swap (LN to On-Chain)
A scenario where a user has Lightning liquidity and wants it secured in an on-chain cold storage wallet (Submarine Swap "in reverse").
1. **The Setup:** The Swap Provider creates the secret and an on-chain HTLC paying the user's on-chain address.
2. **The Lock:** The Provider generates a Lightning invoice mirroring the hash lock.
3. **The Swap:** The user securely pays the Lightning invoice. The provider sweeps the Lightning funds by revealing the secret. The user observes the revealed secret on the Lightning network and uses it to immediately claim their on-chain HTLC funds.

In both instances, the architecture leverages the fact that the hash and the secret are identical across both the on-chain and off-chain networks. A swap is fundamentally atomic: if a party aborts midway, the timeouts simply expire, and original balances are reclaimed entirely.

---

**References:**
- [[02_Developer_Track/02. Technical Part (Swaps & Layers) - Deep Dive Summary|02. Technical Part (Swaps & Layers) - Deep Dive Summary]]
- [[02_Developer_Track/Swap Layer/HTLCs|Hash Time Locked Contracts (HTLCs)]]
