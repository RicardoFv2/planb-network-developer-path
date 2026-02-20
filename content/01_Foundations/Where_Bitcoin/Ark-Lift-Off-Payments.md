---
title: "Ark (Lift-Off Payments)"
description: "An alternative L2 proposal for Bitcoin payments with improved liquidity and user experience."
tags:
  - bitcoin
  - ark
  - scaling
  - layer2
---

# Ark (Lift-Off Payments)

> [!abstract] TL;DR
> Ark is a trustless, off-chain second layer that allows for private payments without the liquidity management issues of Lightning channels.

## What Is It?

Ark is a newer proposal for a Bitcoin second layer (L2) designed to scale transactional capacity while simplifying the user experience compared to the Lightning Network.

## How It Works

It uses a concept called **"Lift-Off Payments."** Unlike Lightning, which requires users to manage inbound liquidity and payment channels, Ark allows users to send and receive payments using "VTXOs" (Virtual UTXOs) maintained off-chain by Ark Service Providers (ASPs).

## Why Does It Matter?

- **No Channel Management:** Users don't need to open or close channels to start receiving payments.
- **Improved Privacy:** Payments are more private by design, as they are bundled through the ASP.
- **Zero Inbound Liquidity Problem:** Solves one of the biggest friction points for new Lightning users.

## Analogy

If Lightning is like a network of pipes (channels) that you must maintain, Ark is like a **Lift-Off** vessel: you can jump in and out of the off-chain environment without having to build the infrastructure yourself.

## Related Notes

- [[Lightning-Network-Payment-Channels]]
- [[The-Scalability-Trilemma-Bathtub-Curve]]
- [[The-Timechain]]
