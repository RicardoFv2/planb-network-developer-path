---
title: "Taproot & Advanced Scripts"
description: "How Taproot and Musig2 enhance the privacy and efficiency of Submarine Swaps."
tags:
  - developer-track
  - taproot
  - p2tr
  - musig2
  - privacy
---

# Taproot & Advanced Scripts

[[02_Developer_Track/index-MOC#lecture-02|← Return to Index]]

> [!abstract] TL;DR
> Taproot (P2TR) improves Bitcoin's privacy and efficiency by making complex smart contracts look like standard single-signature transactions on-chain. While HTLCs provide atomic security for swaps, they inherently leak smart-contract logic onto the blockchain when executed. The Taproot upgrade (`P2TR`) introduced structural changes to Bitcoin, specifically Schnorr signatures and MAST, enabling swaps to mirror entirely normal user transactions.

## The Problem with Legacy Swaps (P2SH/P2WSH)
Traditionally, Submarine Swaps on-chain required Pay-to-Script-Hash (P2SH) or Pay-to-Witness-Script-Hash (P2WSH). 
When claiming an HTLC locked in these formats, the user must publish the *entire script* containing the IF/ELSE loops, Hash Locks, and CLTV statements to the blockchain. This publicly brands the UTXO as a "Submarine Swap," reducing fungibility and severely harming privacy across the network.

## The Taproot Upgrade (`P2TR`)

Taproot solves the privacy leak by structuring addresses via Merkle Trees (MAST - Merkelized Abstract Syntax Trees) combined with Schnorr signature key aggregation. It allows two distinct spending paths for a single address:

1. **The Key Path (Cooperative):**
   - The user and the swap provider combine their public keys into a single aggregated master public key using an API mapping like **MuSig2**.
   - If both parties sign cooperatively, the transaction aggregates into one normal signature.
   - On-chain, this looks exactly like Alice naturally sending Bitcoin to Bob—maximum privacy and minimum fee.

2. **The Script Path (Uncooperative / Enforcement):**
   - If either the user or the provider disappears or refuses to cooperate, the "Key Path" fails.
   - However, tucked underneath that master key within a cryptographic Merkle root is the complex HTLC logic.
   - The aggrieved party publishes *only the specific script condition* they need (e.g., the Timeout branch or the Hash branch) to enforce the contract and reclaim/sweep the funds.
   - The un-executed branches of the smart contract remain permanently hidden cryptographically.

By making the "script path" a fallback rather than the default, Taproot makes complex smart contracts invisible unless arbitration is actively required.

---

**References:**
- [[02_Developer_Track/02. Technical Part (Swaps & Layers)|02. Technical Part (Swaps & Layers) - Deep Dive Summary]]
