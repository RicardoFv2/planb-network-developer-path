---
title: "Liquid Confidential Transactions (CT)"
description: "How Liquid hides transaction details using blinding keys and cryptographic proofs."
tags:
  - developer-track
  - liquid-network
  - privacy
  - cryptography
---

# Liquid Confidential Transactions

[[02_Developer_Track/index-MOC#lecture-03|← Return to Index]]

> [!abstract] TL;DR
> Confidential Transactions (CT) on the Liquid Network hide the amount and type of asset being transferred from everyone except the sender and receiver, enhancing financial privacy.

## 🕵️ What is Blinded?
Unlike Bitcoin, where the ledger is fully transparent, Liquid uses **Confidential Transactions** to hide:
- **Transaction Amounts:** The number of SATs or assets sent.
- **Asset Types:** Whether you are sending L-BTC, USDt, or a custom token.

## 🔑 How It Works: Blinding Keys
Each Liquid address has two parts:
1. **Spend Key:** Used to authorize the movement of funds.
2. **Blinding Key:** Used to encrypt/decrypt the transaction details on the ledger.

When you send a payment, the SDK generates a shared secret with the receiver. Only the participants with the correct blinding keys can "unblind" the transaction to see the amount.

## 🛡️ Privacy vs. Auditability
- **The Federation:** Validates that no new coins are created out of thin air using "Range Proofs" (cryptographic math), but they never see the actual numbers.
- **Observers:** Can see that a transaction occurred between two addresses, but they see the amount as "Confidential."
- **Recipients:** The Breeze SDK automatically handles the unblinding process using the wallet's master blinding key, so the user sees their balance normally.

## 📊 Comparison: Bitcoin vs. Liquid

| Feature | Bitcoin (Base Layer) | Liquid (Sidechain) |
| :--- | :--- | :--- |
| **Visibility** | Public & Transparent | Blinded & Confidential |
| **Amounts** | Exposed to all | Hidden via Range Proofs |
| **Assets** | Native BTC only | Multi-asset (all blinded) |
| **Linkability** | High (Chain Analysis) | Low (Blinded metadata) |

---

**References:**
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
