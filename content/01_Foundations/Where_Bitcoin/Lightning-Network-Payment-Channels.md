---
title: "Lightning Network (Payment Channels)"
description: "A Layer 2 scaling solution for instant, cheap, and private Bitcoin payments."
tags:
  - bitcoin
  - lightning
  - scaling
  - layer2
---

# Lightning Network (Payment Channels)

> [!abstract] TL;DR
> The Lightning Network enables instant Bitcoin payments through off-chain payment channels, settling only the net result on the Timechain.

## What Is It?

The Lightning Network is a Layer 2 scaling solution built on top of Bitcoin. It uses **Payment Channels** to allow users to transact instantly and cheaply without settling every transaction on the main chain.

## How It Works

1.  **Opening:** Two parties lock funds into a multisig address on the main chain. This is the "channel."
2.  **Transacting:** They can update the balance of who owns what within that channel instantly, millions of times. These updates are valid Bitcoin transactions that are _not_ broadcasted yet.
3.  **Closing:** Either party can close the channel, broadcasting the final state to the main chain. The miners only see the net result.

## Why Does It Matter?

- **Instant Settlement:** No need to wait 10 minutes for confirmations.
- **Microtransactions:** Fees are negligible, enabling streaming payments (e.g., pay per second of video).
- **Privacy:** Intermediate hops in a payment route (onion routing) don't know who the sender or receiver is.

## Evolution

- **HTLCs (Hash Time Locked Contracts):** The current standard for routing payments.
- **PTLCs (Point Time Locked Contracts):** An upgrade (using Schnorr signatures) that improves privacy by making payments decorrelatable.

## Related Notes

- [[The-Scalability-Trilemma-Bathtub-Curve]]
- [[Ark-Lift-Off-Payments]]
- [[The-Timechain]]

[[index|← Return to Index]]
