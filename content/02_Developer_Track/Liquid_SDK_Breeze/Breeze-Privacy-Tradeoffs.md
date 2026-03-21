---
title: "Privacy Trade-offs & Security Models"
description: "Analyzing the non-custodial vs. third-party trust dynamics in Breeze and Liquid."
tags:
  - developer-track
  - privacy
  - security
  - non-custodial
---

# Privacy Trade-offs & Security Models

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> Using an SDK necessarily involves relying on abstractions provided by third parties. Breeze mitigates this by maintaining a non-custodial architecture where keys never leave the device, while acknowledging the inherent trade-offs of sidechains.

## 🔒 Non-Custodial Foundations
- **Local Keys:** The mnemonic (12/24 words) and private keys are generated and stored exclusively on the user’s device. Breeze or any swap provider never sees the seeds.
- **Self-Hosting:** Metadata synchronization services (Cloud Sync) can be self-hosted by users who wish to remove reliance on Breeze's default servers.

## 🕵️ Privacy Features
- **Confidential Transactions (CT):** On the Liquid network, the blockchain recorded data is blinded. Only the sender and receiver know the amount and asset type. Neither the federation nor an observer can "see" your balance.
- **Swap Privacy:** While a swap reveals the script to the blockchain (showing that a swap occurred), the link between the on-chain BTC and the lightning recipient is broken by the swap provider.

## ⚠️ The Trade-offs
- **Federated Trust:** Liquid users trust a group of 15 functionaries. While collusion is unlikely and "Emergency Withdrawals" are technically possible, it is not "trustless" in the same way the Bitcoin base layer is.
- **Swapping Reliance:** If a swap provider (like Boltz) goes offline, you cannot execute new cross-layer payments. However, existing "locked" funds are protected by **Refund Flows** (time-locks), ensuring you can recover your money after the lock period expires.
- **Metadata Sync:** If using the default Breeze sync service, the provider knows *when* you are online and potentially which encrypted blobs belong to which IP, though the data inside is encrypted.

---

**References:**
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
