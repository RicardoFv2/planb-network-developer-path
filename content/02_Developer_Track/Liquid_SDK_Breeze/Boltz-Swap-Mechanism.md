---
title: "Boltz Swap Mechanism"
description: "The technical bridge connecting the Liquid and Lightning networks."
tags:
  - developer-track
  - liquid-network
  - lightning-network
  - htlc
  - boltz
---

# Boltz Swap Mechanism

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> To enable Lightning payments without a native Lightning node, the Breeze SDK uses **Boltz**, a non-custodial swapping service. This allows users to "swap" L-BTC for Lightning SATs (and vice versa) atomically.

## 🛠️ The Swap Flow (Send Payment)
When a user pays a Lightning invoice using the Liquid SDK:
1. **Lockup:** The user's wallet locks L-BTC into a special script (HTLC) on the Liquid chain. Only Boltz can claim this if they provide proof of paying the Lightning invoice.
2. **Payment:** Boltz pays the Lightning invoice across the Lightning network and receives a "Preimage" (the proof of payment).
3. **Claim:** Boltz uses the Preimage to claim the locked-up L-BTC on the sidechain.

## 🛡️ Security: The Refund Flow
What if Boltz takes the L-BTC but never pays the invoice?
- **Time-locks:** The lockup script includes a timeout (e.g., 4 hours).
- **Refund:** If Boltz doesn't provide the preimage before the timeout, the user can use the SDK's `refund` method to take their L-BTC back. 
- **Non-Custodial:** At no point does Boltz have full control over the user's funds without providing proof of service.

## 📊 Trust Assumptions
While the process is cryptographic, there are minor trade-offs:
- **Availability:** If Boltz is offline, you cannot start a new swap.
- **Liquidity:** You rely on Boltz having enough Lightning liquidity to facilitate your transaction.
- **Cost:** Boltz charges a fee (usually a small percentage) for the service.

## 💡 Why Boltz?
By using Boltz, Breeze removes the need for **Outbound Liquidity Management**, channel rebalancing, and maintaining a 24/7 online node presence. It makes Bitcoin payments "Just Work."

---

**References:**
- [[02_Developer_Track/01. Bitcoin Protocol Intro - Deep Dive Summary|01. Bitcoin Protocol Intro]]
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
