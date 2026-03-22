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

[[02_Developer_Track/index-MOC#lecture-03|← Return to Index]]

> [!abstract] TL;DR
> Liquid is a multi-asset sidechain that can host not only Bitcoin (L-BTC) but also stablecoins (USDt), security tokens, and other digital assets on a unified ledger.

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
