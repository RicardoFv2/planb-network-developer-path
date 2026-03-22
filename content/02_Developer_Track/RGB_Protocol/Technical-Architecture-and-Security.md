---
title: "Technical Architecture and Security"
description: "Deep dive into the security model of RGB compared to altcoins and the importance of decentralization."
tags:
  - developer-track
  - rgb-protocol
  - security
  - decentralization
---

# Technical Architecture and Security

[[02_Developer_Track/05. RGB Protocol - Deep Dive Summary|← Return to Summary]]

The RGB protocol is built on a foundation of security and decentralization, addressing the fundamental trade-offs made by other asset platforms.

### The Problem with Altcoins
Federico highlights several critical issues with using altcoins (Ethereum, Solana, etc.) for asset issuance:
- **Centralization:** Many altcoins sacrifice decentralization for throughput, leading to a small set of validators and high reliance on third-party nodes.
- **Security Trade-offs:** Proof-of-Stake (PoS) models the security based on the token's value, which can be more fragile than Bitcoin's Proof-of-Work.
- **Censorship Resistance:** With more centralized node infrastructure, altcoins are more susceptible to censorship at the network and validator levels.

### The RGB Solution
RGB is designed to be a "Bitcoin-based alternative" that does not compromise on trust assumptions:
- **No Federations:** RGB does not require a central authority or a federation of validators.
- **Zero Blockchain Bloat:** Since data is off-chain, RGB does not increase the cost of running a Bitcoin node.
- **Censorship Resistance:** Miners cannot see the contents of RGB commitments, making it impossible for them to selectively censor RGB transactions.

### Commitment Schemes
RGB supports multiple ways to anchor commitments into Bitcoin transactions:
1. **OP_RETURN:** Committing to the hash of the RGB transition in a standard Bitcoin output. Simple to implement but potentially visible.
2. **Taproot (Opret):** Using Taproot's script tree to hide the commitment. This provides superior privacy and makes RGB transactions indistinguishable from normal Bitcoin spends.

---
[[02_Developer_Track/index-MOC#lecture-05|← Return to Index]]
