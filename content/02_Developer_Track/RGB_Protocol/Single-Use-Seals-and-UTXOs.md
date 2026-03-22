---
title: "Single-Use Seals and UTXOs"
description: "Understanding the core mechanism of RGB: Single-use seals and their anchoring in Bitcoin UTXOs."
tags:
  - developer-track
  - rgb-protocol
  - utxo
  - single-use-seals
---

# Single-Use Seals and UTXOs

[[02_Developer_Track/05. RGB Protocol - Deep Dive Summary|← Return to Summary]]

Single-use seals are the heart of the RGB protocol. They provide a standardized way to represent and transfer ownership of off-chain assets using the Bitcoin UTXO model.

### The Piggy Bank Analogy
- A **Bitcoin UTXO** (Unspent Transaction Output) can be thought of as a **piggy bank** or a sealed box.
- To spend the Bitcoin, you must destroy (spend) the UTXO.
- In RGB, we **assign** assets to these UTXOs. To move the asset, you must spend the underlying UTXO.
- Since a UTXO can only be spent **once**, it acts as a "single-use seal." Once broken, the asset must be reassigned to a new UTXO (seal).

### How it Works in Practice
1. **Issuance:** An issuer creates a contract and assigns the initial supply of tokens to a set of Bitcoin UTXOs.
2. **Transfer:** The owner of the UTXO creates an "Ownership Transfer" message. This message specifies the new UTXOs that will now "own" the assets.
3. **Commitment:** The hash of this transfer message is committed inside a Bitcoin transaction that spends the original UTXO.
4. **Verification:** The receiver checks the Bitcoin blockchain to ensure the transaction spending the original UTXO was confirmed. This guarantees that the "seal" was used and the assets were moving.

### Benefits
- **Double-Spending Prevention:** By tethering the asset to a UTXO, RGB inherits the double-spending protection of the Bitcoin network.
- **Modular Ownership:** Assets can be assigned to any UTXO, even those controlled by complex scripts like multi-sigs or time-locks.
- **Efficiency:** The assets and Bitcoins move in the same "box," but they don't have to share the same destiny; you can move the assets while keeping the satoshis, or vice versa (though practically you move them together by spending the UTXO).

---
[[02_Developer_Track/index-MOC#lecture-05|← Return to Index]]
