---
title: "Transaction Malleability & SegWit"
description: "How Segregated Witness solved the critical malleability bug limiting the Lightning Network."
tags:
  - developer-track
  - segwit
  - lightning-network
---

# Transaction Malleability & SegWit

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> Transaction Malleability was a flaw where the cryptographic signature of a transaction could be slightly altered without invalidating it, changing the Transaction ID (TXID). Segregated Witness (SegWit) fixed this by moving the signature outside the TXID hash, making protocols like the Lightning Network possible.

## The Malleability Problem
In legacy Bitcoin transactions, everything—including the digital signature—was hashed to generate the unique identifier for the transaction (the TXID).
- **The Exploit:** A malicious node or miner could slightly modify the cryptographic encoding of the signature (e.g., tweaking ECDSA parameters). The signature remained mathematically valid and spent the identical UTXOs to the identical destinations.
- **The Consequence:** Because the signature string changed, the resulting TXID hash changed.

## Why Malleability Broke Lightning
The Lightning Network relies on chains of unconfirmed transactions. To open a channel, Alice and Bob exchange refund transactions that spend from an unconfirmed funding transaction.
If the funding transaction's TXID changed *while sitting in the mempool* due to malleability, any child transactions relying on that specific TXID became invalid orphans. This made it impossible to safely enforce state channels.

## The SegWit Solution
Segregated Witness (`SegWit v0`) solved this by splitting ("segregating") the transaction into two parts:
1. **The Core Data:** Inputs, outputs, amounts. This is hashed to create the TXID.
2. **The Witness Data:** Signatures and unlocking scripts. This is moved entirely outside the TXID calculation.

Because the signature is no longer part of the TXID hash, altering it no longer changes the transaction's identifier. This guarantees that unconfirmed transaction chains (like Lightning channels) are stable and reliable.

As a bonus, SegWit introduced a "block weight" discount for witness data, making complex scripts economically cheaper to execute.

---

**References:**
- [[02_Developer_Track/02. Technical Part (Swaps & Layers) - Deep Dive Summary|02. Technical Part (Swaps & Layers) - Deep Dive Summary]]
