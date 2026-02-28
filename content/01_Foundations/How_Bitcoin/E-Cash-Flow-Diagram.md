---
title: "E-Cash Flow Diagram"
description: "The interaction between User, Merchant, and Bank in a traditional eCash system."
tags:
  - ecash
  - economics
  - history
---

[[index|← Return to Index]]

# E-Cash Flow Diagram

> [!abstract] TL;DR
> Traditional eCash involves a three-way interaction where a bank handles the issuance and verification while blind signatures protect user privacy.

## The Cycle

1.  **Withdrawal:** The User sends a "blinded" serial number to the **Bank** along with fiat money. The Bank signs it and returns it.
2.  **Unblinding:** The User unblinds the coin. They now have a coin signed by the Bank with a serial number only the User knows.
3.  **Payment:** The User gives the coin to a **Merchant**.
4.  **Verification:** The Merchant sends the coin to the **Bank** to ensure it hasn't been spent before (**Double Spend Check**).
5.  **Settlement:** If valid, the Bank credits the Merchant's account and records that serial number as "spent."

## Why It Failed

While the Bank couldn't see _what_ the User was buying (privacy), the Bank was still a **Centralized Authority**.

- It could stop the withdrawal.
- It could stop the verification.
- If the Bank's server went down, the money became worthless.

## Evolution to Bitcoin

Bitcoin removed the "Bank" in the middle. Instead of a central server checking for double-spends, the **Timechain** (Proof of Work) allows every node to check for double-spends collectively.

## Related Notes

- [[David-Chaum-and-eCash]]
- [[Blind-Signatures-for-Privacy]]
- [[The-Double-Spending-Problem]]

#ecash #economics #history #centralization

[[index|← Return to Index]]
