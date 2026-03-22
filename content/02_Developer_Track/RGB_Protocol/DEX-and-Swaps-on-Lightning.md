---
title: "DEX and Swaps on Lightning"
description: "How RGB enables decentralized exchanges and atomic swaps over the Lightning Network without KYC or front-running risks."
tags:
  - developer-track
  - rgb-protocol
  - lightning-network
  - dex
  - swaps
---

# DEX and Swaps on Lightning

[[02_Developer_Track/05. RGB Protocol - Deep Dive Summary|← Return to Summary]]

The integration of RGB with Lightning Network doesn't just enable payments; it creates the foundation for a truly **Decentralized Exchange (DEX)**.

### Routing as a Swap Mechanism
In the Lightning Network, routing is essentially a series of swaps. When a payment of 1 BTC goes through a hop, the intermediate node swaps 1 BTC in one channel for 1 BTC in another.
With RGB, we can break the **assumption of fungibility**:
- **Asset Swaps:** A node can receive BTC and send out USDT (at a negotiated exchange rate).
- **Circular Transactions:** Two parties can swap assets by routing a transaction through each other or a common peer.

### Benefits over Ethereum/EVM DEXs
1. **Privacy:** Swaps are entirely private. No blockchain observer can see the trade, the size, or the assets involved.
2. **No Front-Running (MEV):** Because transactions are not in a public mempool, miners cannot see them and front-run them.
3. **Efficiency:** Swaps happen instantly with minimal fees, unlike the high gas costs of on-chain AMMs.
4. **No Custody:** Users maintain full control of their private keys throughout the swap process.

### Use Case: Cross-Asset Payments
Imagine a user who only holds Bitcoin but wants to pay a merchant who only accepts USDT.
- The user sends Bitcoin over Lightning.
- An intermediate node (acting as a "liquidity provider") converts the Bitcoin to USDT.
- The merchant receives USDT instantly.
- The user never had to touch an exchange or perform KYC for this specific payment.

---
[[02_Developer_Track/index-MOC#lecture-05|← Return to Index]]
