---
title: "Liquid Multi-Asset Support"
description: "Utilizing Liquid for stablecoins, security tokens, and multi-asset payments via Breeze."
tags:
  - developer-track
  - liquid-network
  - usdt
  - assets
---

# Liquid Multi-Asset Support

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> Liquid is a "Multi-Asset" sidechain. This means it can host any number of digital assets (like USDt or LBTC) on the same ledger, benefiting from the same speed and privacy features.

## 💵 Stablecoins: USDt on Liquid
One of the most common use cases for the Liquid SDK is the integration of **USDt (Tether)**. 
- **Low Cost:** Sending USDt on Liquid is significantly cheaper than on Ethereum (ERC-20) or Tron.
- **Atomic Swaps:** Because USDt and L-BTC live on the same chain, they can be swapped "atomically" (either both happen or neither does) without a trusted middleman.

## 🎨 Asset Issuance
Developers can issue their own assets on Liquid using the SDK or command-line tools:
- **Security Tokens:** Digital bonds or equity.
- **Collectibles:** Non-fungible assets.
- **Loyalty Points:** Internal application tokens.

## 🔄 Cross-Asset Payments
The Breeze SDK abstracts the complexity of assets. If an application requires a payment in USDt, the SDK can:
1. **Prepare:** Query swap providers (like SideSwap) for the BTC/USDt exchange rate.
2. **Execute:** Perform the swap and the payment in a single logical flow.

## 🚀 Why Use Multi-Asset?
- **Universal Interface:** The same "Connect-Prepare-Execute" paradigm works for BTC and USDt.
- **Confidentiality:** Just like BTC, the *type* of asset and the *amount* are hidden from the public via Confidential Transactions.

---

**References:**
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
