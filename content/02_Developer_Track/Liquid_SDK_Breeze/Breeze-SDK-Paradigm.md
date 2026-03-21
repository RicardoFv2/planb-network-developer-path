---
title: "Breeze SDK Paradigm: Connect, Prepare, Execute"
description: "An in-depth look at the three-step workflow that standardizes Bitcoin payment integration."
tags:
  - developer-track
  - breeze-sdk
  - api-design
---

# Breeze SDK Paradigm: Connect, Prepare, Execute

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> To handle the dynamic nature of Bitcoin fees and the complexities of swapping across layers, the Breeze SDK uses a standardized three-step workflow: **Connect**, **Prepare**, and **Execute**.

## 🔌 1. Connect (Initialization)
Before any operation, the SDK must be initialized. This step:
- Starts the internal Rust engine.
- Establishes connections to the Bitcoin/Liquid nodes.
- Synchronizes the local wallet state with the blockchain.
- Sets up background handlers for swaps and refunds.

## 📝 2. Prepare (Validation)
The `prepare` phase is the most critical for User Experience (UX). Instead of just "sending" money, the developer calls a `prepare` method (e.g., `prepareSendPayment`).
- **Fee Discovery:** It queries the network or swap provider to find the exact cost of the transaction.
- **Validation:** It checks if the destination (Bolt 11, Bolt 12, Liquid address, or BTC address) is valid and if the wallet has sufficient funds.
- **User Confirmation:** It returns a "Preparation Object" containing the breakdown of fees. The developer uses this to show the user exactly what will happen before it happens.

## 🚀 3. Execute (Finalization)
Once the user confirms, the developer passes the "Preparation Object" into the `execute` method (e.g., `executeSendPayment`).
- **Atomicity:** The SDK handles the cryptographic signing and broadcasting.
- **Success/Failure:** It returns the final payment status, including the preimage or transaction ID.

## Why This Matters
This paradigm abstracts over **23,000 lines of Rust code**. It ensures that whether you are paying a Lightning invoice or a on-chain Liquid address, the code you write looks exactly the same:
```javascript
// A conceptual example of the "atomic" workflow
const prepareResponse = await sdk.prepareSendPayment({ destination, amount });
console.log(`The fee is ${prepareResponse.fees}`);
// ... wait for user click ...
const result = await sdk.executeSendPayment({ prepareResponse });
```

---

**References:**
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
