---
title: "Spectrum of Security Models"
description: "Why security in Bitcoin is not binary but a spectrum of models with trade-offs."
tags:
  - bitcoin
  - foundations
  - security
  - sovereignty
---

# Spectrum of Security Models

[[index|← Return to Index]]

> [!abstract] TL;DR
> In the modern Bitcoin ecosystem, security is not binary. Each layer solves a specific problem (speed, privacy, costs) by assuming temporal or validation trade-offs against the main chain.

## Not Your Keys, Not Your Coins (The Spectrum)

As the ecosystem has grown more complex, the simplistic purity of "Not your keys, not your coins" has given way to a sophisticated technical spectrum. A user now chooses a security model that balances security, privacy, and convenience based on their specific needs.

1.  **Full Custody:** High counterparty risk (Exchanges).
2.  **Federated Multisig:** Medium counterparty risk, better privacy (Liquid, E-cash).
3.  **Statechains:** A blind federation transferring UTXO ownership.
4.  **Payment Channels:** No direct custodial risk, but requires active monitoring (Lightning Network).
5.  **Arks:** Asynchronous batching needing an ASP temporarily.
6.  **Base Layer:** Total sovereignty, highest security, slowest and most expensive (Cold Storage).

## The Trade-Offs

Security in Bitcoin is a spectrum where:

- Greater convenience often requires greater trust.
- Lower fees or faster settlements often necessitate moving to Layer 2 or higher models that entail different assumptions regarding liveness or counterparty validation.

## Related Notes

- [[Custodial-vs-Federated-Models]]
- [[Layer-2-Security-Models]]
- [[Base-Layer-Sovereignty]]

#bitcoin #security #tradeoffs #layers
