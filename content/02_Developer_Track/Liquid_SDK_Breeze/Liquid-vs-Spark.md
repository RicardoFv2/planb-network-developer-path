---
title: "Sidechain Comparison: Liquid vs. Spark"
description: "Choosing the right secondary layer for Bitcoin payments within the Breeze ecosystem."
tags:
  - developer-track
  - liquid-network
  - spark-network
---

# Sidechain Comparison: Liquid vs. Spark

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> Breeze offers two primary modern SDK implementations: Liquid and Spark. While they both facilitate Lightning payments via swaps, they rely on different underlying architectures with distinct advantages.

## 💧 The Liquid Network SDK
Liquid is a federated sidechain managed by a group of financial institutions and Bitcoin companies (The Federation).
- **Asset Support:** Can issue and trade assets beyond Bitcoin, such as stablecoins (USDt) or digital bonds.
- **Confidentiality:** Uses "Confidential Transactions" to hide amounts and asset types from the public ledger.
- **Trade-off:** Requires trusting that the Federation (15 nodes) will not collude to freeze the 1:1 BTC peg (though fail-safe mechanisms exist).

## ⚡ The Spark Network SDK
Spark is a newer layer-two solution integrated into the Breeze ecosystem in 2025.
- **User Experience:** Focuses on even lower friction than Liquid, aiming for "instant" feel across all transaction types.
- **Network Architecture:** Designed to minimize the common pain points of standard Lightning (like outbound liquidity management) by using a more fluid secondary layer.
- **Interface Stability:** One major goal of Spark was to maintain an interface almost identical to the Liquid SDK, allowing developers to switch with minimal code changes.

## 📊 Summary Table

| Feature | Liquid SDK | Spark SDK |
| :--- | :--- | :--- |
| **Primary Use** | Privacy & Multi-assets | Speed & UX |
| **Privacy** | High (Confidential Trans.) | High (Layer 2) |
| **Complexity** | Moderate | Very Low |
| **Trust Model** | Federated (15 nodes) | Layer 2 Operator |
| **Maturity** | Battle-tested (2024) | Cutting-edge (2025) |

---

**References:**
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
