---
title: "The UTXO Model vs Account Model"
description: "Understanding Bitcoin's 'Unspent Transaction Output' model versus traditional bank accounts."
tags:
  - bitcoin
  - structure
  - technology
---

# The UTXO Model vs Account Model

[[index|← Return to Index]]

> [!abstract] TL;DR
> Bitcoin doesn't have "accounts." It tracks ownership through UTXOs (Unspent Transaction Outputs), which are like digital gold nuggets that must be spent in their entirety.

## Account Model (Standard Bank/Ethereum)

- **Concept:** Your identity (Account) has a balance (e.g., $100).
- **Transaction:** You subtract $10 from your balance and add $10 to someone else's.
- **Analogy:** A digital whiteboard where the bank erases your number and writes a new one.

## UTXO Model (Bitcoin)

- **Concept:** There are no "accounts." There are only "fragments" of bitcoin called **UTXOs**. Your "balance" is simply the sum of all UTXOs that your private key can unlock.
- **Transaction:** You take a UTXO (e.g., 1 BTC), "melt" it down, and create new UTXOs (e.g., 0.1 BTC to the recipient and 0.9 BTC back to yourself as change).
- **Analogy:** Physical cash. If you have a $20 bill and want to buy something for $5, you cannot "tear" the bill. You must give the whole $20 and receive $15 back in change.

## Why This Matters

- **Privacy:** One user can own thousands of UTXOs that aren't obviously linked to each other.
- **Security:** Transactions can be processed in parallel because they only affect specific outputs, not a global account state.
- **Auditability:** It makes it much easier to verify that no new coins were created out of thin air.

## Related Notes

- [[Satoshi-Nakamoto-The-Final-Synthesis]]
- [[Digital-Signatures-and-Authorship]]
- [[The-Timechain]]

#bitcoin #structure #technology #utxo
