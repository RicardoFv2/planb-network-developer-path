---
title: "What is RGB?"
description: "An introduction to the RGB protocol, asset tokenization, and client-side validation on Bitcoin."
tags:
  - developer-track
  - rgb-protocol
  - bitcoin-assets
---

# What is RGB?

[[02_Developer_Track/05. RGB Protocol - Deep Dive Summary|← Return to Summary]]

RGB is a suite of protocols for scalable and private smart contracts for Bitcoin and Lightning. It allows for the issuance and transfer of assets (tokens) using Bitcoin's security without requiring changes to the Bitcoin protocol itself.

### Key Concepts

1. **Asset Tokenization:** RGB enables the creation of fungible tokens (like USDT) and non-fungible tokens (NFTs) on top of Bitcoin.
2. **Client-Side Validation:** Unlike traditional blockchains where every node validates every transaction, RGB only requires the parties involved in a transaction to validate its specific history.
3. **Double-Spending Protection:** RGB leverages the Bitcoin blockchain as a "commitment layer." State transitions are anchored in Bitcoin transactions, ensuring that assets cannot be spent twice.
4. **Off-Chain Data:** The actual data of the smart contracts and asset transfers remains off-chain, shared only between users.

> [!NOTE]
> RGB doesn't "color" satoshis; it assigns assets to Bitcoin UTXOs. The assets and the underlying satoshis move independently.

### Benefits over Altcoins
- **Inherited Security:** It uses the strongest security model in existence (Bitcoin Proof-of-Work).
- **Infinite Scalability:** Validation happens at the edge, scaling with the number of participants rather than the size of the blockchain.
- **Enhanced Privacy:** Transactions are not visible to the public or miners.

---
[[02_Developer_Track/index-MOC#lecture-05|← Return to Index]]
