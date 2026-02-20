---
title: "Hal Finney and RPOW (Reusable Proof of Work)"
description: "How Hal Finney made Proof of Work tokens transferable and reusable."
tags:
  - history
  - pow
  - cypherpunks
---

# Hal Finney and RPOW (Reusable Proof of Work)

> [!abstract] TL;DR
> Hal Finney's RPOW made Proof of Work tokens reusable, acting as a direct predecessor to Bitcoin's transaction model.

## What Is It?

In 2004, Hal Finney created **Reusable Proof of Work (RPOW)**. Before RPOW, Proof of Work (like Hashcash) was used once to stop spam and then discarded. Finney realized that if you could "wrap" a PoW token and transfer it, it could function as a form of money.

## Why Does It Matter?

- **Transferable Energy:** It was the first system to treat Proof of Work as a bearer asset that could be traded between users.
- **Trusted Hardware:** To prevent double-spending without a global ledger, RPOW used **IBM 4758 Secure Coprocessors**. You had to trust that the hardware was secure and that Hal hadn't tampered with it.
- **First Bitcoiner:** Hal was the first person (besides Satoshi) to run the Bitcoin software and received the first-ever Bitcoin transaction. Many believe he was a key contributor to the protocol's design.

## Evolution

RPOW was the missing link between **Hashcash** (burning energy) and **Bitcoin** (tracking energy ownership on a chain). Bitcoin replaced the "Secure Coprocessor" with the **Decentralized Timechain**, removing the need to trust any hardware manufacturer.

## Related Notes

- [[Hashcash-and-Linear-Cost]]
- [[Satoshi-Nakamoto-The-Final-Synthesis]]
- [[The-Double-Spending-Problem]]

#history #pow #cypherpunks #innovation
