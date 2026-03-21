---
title: "Bitcoin Layers & Fragmentation"
description: "Overview of the scalability trilemma, secondary layers, and liquidity fragmentation."
tags:
  - developer-track
  - layer-2
  - scaling
---

# Bitcoin Layers & Fragmentation

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> Bitcoin’s base layer optimizes for absolute security and decentralization at the cost of high throughput. To scale to a global medium of exchange, transactions must occur on secondary layers.

## The Scalability Trilemma
The blockchain trilemma states that a decentralized network can only optimize for two of the three properties: **Decentralization, Security, and Scalability**. 
Bitcoin explicitly sacrifices base-layer scalability. Blocks are capped in size and spaced every ~10 minutes to ensure that commodity hardware can validate the chain, thus preserving extreme decentralization.

## The Multi-Layer Vision
Since the base chain cannot verify every coffee purchase on Earth, smaller, faster transactions migrate to distinct secondary layers:
- **The Lightning Network:** A network of bidirectional payment channels providing instant, nearly free settlement.
- **Liquid Network:** A federated sidechain enabling confidential transactions and rapid block times (1 minute).
- **Chaumian Mints (Ecash):** Blinded centralized or federated servers (e.g., Fedimint, Cashu) that issue private tokens backed by Bitcoin.
- **Rollups and L2 statechains:** Cryptographic off-chain settlement models exploring zero-knowledge scaling on Bitcoin.

## The Fragmentation Issue
Every new layer introduced to the Bitcoin ecosystem creates a silo. 
For example, Bitcoin on Liquid is not inherently aware of Bitcoin on Lightning. If a user holds L-BTC but wishes to pay a Lightning invoice, they cannot do so directly without a bridge. This severely fragments liquidity, harming the user experience as individuals must manage fragmented wallets, handle inbound channel capacities, or rely on centralized exchanges to move capital between layers.

The solution to this fragmentation is **Submarine Swaps**, which construct trustless bridges to shift capital fluidity between these environments seamlessly.

---

**References:**
- [[02_Developer_Track/02. Technical Part (Swaps & Layers)|02. Technical Part (Swaps & Layers) - Deep Dive Summary]]
