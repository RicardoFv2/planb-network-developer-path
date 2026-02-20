---
title: "Layer 2 Security Models"
description: "Security trade-offs of Statechains, Lightning Network, and Arks."
tags:
  - bitcoin
  - foundations
  - security
  - layer2
---

# Layer 2 Security Models

> [!abstract] TL;DR
> Layer 2 solutions (Statechains, Lightning, Arks) eliminate direct custodial risk but introduce new operational requirements like active monitoring or temporary reliance on a provider.

## 1. Statechains

- **Mechanism:** A blind federation facilitates the transfer of the _private key_ ownership corresponding to a specific UTXO off-chain, rather than transferring the unspent output itself on-chain.
- **Security:** Provides scale and privacy. However, a significant tail risk exists where the federation could theoretically collude with past participants in a chain of transfers to steal the funds, although this is cryptographically difficult to execute.

## 2. Payment Channels (Lightning Network)

- **Mechanism:** Bilateral channels are established on-chain. Subsequent transactions update the local balances cryptographically off-chain.
- **Security:** **No direct custodial risk.** You hold the keys.
- **Trade-offs:**
  - You must remain online (liveness) to send/receive.
  - You are subject to censorship by the specific channel you are connected to (though routing mitigates this).
  - Requires active monitoring (running a node yourself or hiring _watchtowers_) to ensure your counterparty doesn't publish an outdated, favorable state to the blockchain.

## 3. Arks

- **Mechanism:** Provides asynchronous batching of payments by an Ark Service Provider (ASP).
- **Security:** Reduces Layer 1 fees and mitigates the inbound liquidity problems inherent to Lightning.
- **Trade-offs:** You rely on the ASP temporarily to facilitate the "lift-off" and settlement. It is non-custodial in the final state but requires interacting with an interactive third party.

## Related Notes

- [[Spectrum-of-Security-Models]]
- [[Lightning-Network-Payment-Channels]]
- [[Ark-Lift-Off-Payments]]
