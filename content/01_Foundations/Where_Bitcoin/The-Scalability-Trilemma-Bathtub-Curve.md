---
title: "The Scalability Trilemma (Bathtub Curve)"
description: "The inherent trade-offs between decentralization, security, and scalability in blockchain design."
tags:
  - bitcoin
  - scaling
  - decentralization
---

# The Scalability Trilemma (Bathtub Curve)

> [!abstract] TL;DR
> Bitcoin prioritizes decentralization and security over base-layer speed, scaling through layers rather than compromising its core properties.

## What Is It?

The Scalability Trilemma suggests that a blockchain can only optimize for two of three major properties: **Decentralization**, **Security**, and **Scalability** (throughput).

- If you increase the block size (scaling), you increase the cost of running a node (centralization).
- If you decrease security (shorter block times), you increase the risk of double-spending or forks.

## Why Does It Matter?

Bitcoin chooses to remain "slow" at the base layer to ensure that anyone with modest hardware can run a node. This makes the network resistant to capture and censorship. Scalability is achieved not by bloating the base layer, but by building fast, cheap layers (like Lightning) on top of it.

## Analogy: The Bathtub Curve

Imagine a **Bathtub**:

- **The Inlet:** New data/transactions flowing in.
- **The Outlet:** The processing power/bandwidth of a single node.
- **The Result:** If you pump data in faster than the weakest node can drain (process) it, the system "overflows," and nodes start falling out of sync, leading to centralisation (only "super-nodes" survive).

## Related Notes

- [[The-Timechain]]
- [[Lightning-Network-Payment-Channels]]
- [[Ark-Lift-Off-Payments]]

[[index|← Return to Index]]
