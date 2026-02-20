---
title: "Custodial vs Federated Models"
description: "Understanding the difference between full custody exchanges and federated multisig solutions."
tags:
  - bitcoin
  - foundations
  - security
  - custody
---

# Custodial vs Federated Models

> [!abstract] TL;DR
> While full custody relies entirely on a single entity's legal guarantees, federated models distribute trust among a consortium for increased privacy and resilience.

## Full Custody

- **The Model:** Relying on a centralized bank, broker, or exchange (e.g., Binance, Coinbase) to hold your bitcoin.
- **The Risk:** You possess **zero cryptographic security** over the funds. Your "balance" is merely an entry in their internal database, backed only by legal guarantees.
- **Counterparty Risk:** Extremely high. Susceptible to internal fraud, hacking, bankruptcy, or regulatory seizures.

## Federated Multisig (Liquid/E-cash)

- **The Model:** You deposit funds into a system managed by a consortium or federation. Examples include Liquid (a sidechain) or Chaumian e-cash mints (like Fedimint).
- **The Mechanism:** A specific quorum (e.g., 11 out of 15 federation members) must actively collude to confiscate or move the funds.
- **The Trade-off:** While you still **trust** third parties, the trust is distributed. These systems often provide drastically better privacy (like blinding signatures in e-cash) or faster inter-exchange settlement (like Liquid) than the base layer, but they are fundamentally not sovereign.

## Related Notes

- [[Spectrum-of-Security-Models]]
- [[Base-Layer-Sovereignty]]
