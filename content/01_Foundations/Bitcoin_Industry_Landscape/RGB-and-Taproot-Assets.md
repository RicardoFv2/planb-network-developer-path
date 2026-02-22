---
title: "RGB and Taproot Assets"
description: "Client-side validation protocols for assets over Bitcoin."
tags:
  - bitcoin
  - foundations
  - architecture
  - assets
---

[[index|← Return to Index]]

# RGB and Taproot Assets

> [!abstract] TL;DR
> RGB and Taproot Assets are client-side validation protocols that allow real-world assets to be represented on Bitcoin without bloating the main chain.

## Client-Side Validation

Historically, attempting to issue tokens on Bitcoin (like Colored Coins or Omni Layer) resulted in bloating the Timechain with non-financial metadata, driving up costs for all users and accelerating the State Bloat problem.

**Client-Side Validation (CSV)** changes this paradigm.

- **How it Works:** Instead of storing the state and history of an asset globally on every Bitcoin node, CSV protocols (like RGB and Taproot Assets) keep this data _off-chain_.
- **The Bitcoin Anchor:** They use Bitcoin transactions merely as cryptographic commitments (anchors) to prove the off-chain state is valid and prevent double-spending.
- **The Benefit:** If Alice sends Bob a "digital dollar" (stablecoin) via RGB, only Alice and Bob need to verify the complex contract history of that specific dollar. The global network only sees a standard Bitcoin transaction, drastically saving on-chain data and preserving privacy.

## Related Notes

- [[Bitcoin-Network-Layers]]
- [[The-Scalability-Trilemma-Bathtub-Curve]]
