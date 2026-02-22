---
title: "Bitcoin Network Layers"
description: "Overview of the layered network stack of Bitcoin (L1, L2, RGB, Nostr)."
tags:
  - bitcoin
  - foundations
  - architecture
  - layers
---

[[index|← Return to Index]]

# Bitcoin Network Layers

> [!abstract] TL;DR
> Bitcoin is evolving from a simple monolithic ledger into a layered network stack, similar to the Internet model (IP -> TCP -> HTTP).

## The Layered Stack

To scale globally without sacrificing decentralization at the base layer, the Bitcoin ecosystem is developing a modular, layered architecture:

- **Base Layer (L1):** The Timechain. Acts as the immutable, global, final settlement system. Everything ultimately anchors back to this foundation.
- **Lighting Network & Arks (L2):** Scalable transaction layers. Provide iterative, instant, and nearly free payments using L1 as a court of final settlement.
- **RGB and Taproot Assets:** Client-side validation protocols. They operate _over_ Bitcoin transactions, allowing the representation of real-world assets (like stablecoins or digital gold) without inflating the main chain with non-monetary data.
- **Nostr (Communication/Identity):** A decentralized relay network. While not strictly a financial layer, it acts alongside Bitcoin to help build trust graphs, manage identity, and route metadata independent of financial nodes (e.g., Zaps linking communication and micro-payments).

## Related Notes

- [[The-Scalability-Trilemma-Bathtub-Curve]]
- [[RGB-and-Taproot-Assets]]

[[index|← Return to Index]]
