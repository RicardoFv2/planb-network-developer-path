---
title: Cashu Programmability (P2PK & HTLC)
aliases: [Spending Conditions, Pay-to-Public-Key, Hash Time Locked Contracts, Lightning Gateways]
tags: [smart-contracts, cashu, programmability, payments, features]
---
# Cashu Programmability (P2PK & HTLC)

[[02_Developer_Track/index-MOC#lecture-04|← Return to Index]]

> [!abstract] TL;DR
> Cashu tokens can be programmed with spending conditions like Pay-to-Public-Key (P2PK) for safe offline receiving or HTLCs for atomic swaps between mints.

By default, eCash tokens are "spendable by everyone." If someone obtains the raw string representing the token, they own it. Cashu introduces **spending conditions**, allowing users to attach scripts to tokens that the mint must enforce before redeeming them.

## Pay-to-Public-Key (P2PK)
P2PK locks an eCash token to a specific recipient's public key. 

### Flow:
1.  **Generate Address**: Carol generates a keypair and sends Alice her public key (the "lock").
2.  **Lock Token**: Alice takes standard eCash, tells the mint to lock it to Carol's public key, and receives the locked token back.
3.  **Transfer**: Alice sends the locked token to Carol.
4.  **Redeem**: Carol sends the locked token to the mint along with a cryptographic signature proving she holds the corresponding private key.
5.  **Unlock**: The mint verifies the signature, removes the lock, and issues Carol fresh, unlocked eCash.

### Use Cases for P2PK:
*   **Offline Receiving**: Because the token is mathematically bound to Carol the moment Alice locks it, Alice physically cannot double-spend it. This means Carol doesn't need an internet connection to safely receive the payment; as long as she has the locked token, only she can ever redeem it.
*   **High-Frequency Payments**: Since the recipient doesn't need to instantly redeem tokens to verify their legitimacy (they are already locked to the recipient), systems like data centers or AI agents can stream thousands of micro-payments per second with zero latency or mint overhead.
*   **Public Zaps**: An eCash token can be published publicly (on Nostr, Twitter, a billboard) locked to the creator's public key. Anyone can view the payment data, but only the creator can claim it.

## Hash Time Locked Contracts (HTLC)
HTLCs operate like P2PK, but instead of a signature, they require a specific hash pre-image (a secret password) to unlock, mirroring exactly how the Lightning Network functions.

### Flow:
1.  **Generate Lock**: Carol generates a secret pre-image and sends Alice the hash of that secret.
2.  **Lock Token**: Alice locks an eCash token with that hash.
3.  **Redeem**: Carol provides the locked token and the original secret pre-image to the mint to unlock it.

### Use Cases for HTLCs:
*   **Multi-Mint Payments**: If Alice has 3,000 sats spread across three different mints (1,000 sats each), she can pay a single 3,000 sat Lightning invoice by constructing a multipath payment. She instructs each mint to send 1,000 sats via an HTLC tied to the same destination invoice hash. 
*   **Atomic Swaps via Lightning Gateways**: HTLCs allow users to trustlessly hire third-party Lightning nodes (Gateways) to pay invoices on their behalf, bypassing the mint's native Lightning node entirely. 

#### Lightning Gateways Explained
1.  Alice wants to pay a Lightning invoice but doesn't want the mint to know.
2.  Alice locks eCash with an HTLC matching the invoice's hash.
3.  Alice gives the locked eCash and the invoice to Bob (a Gateway operator running a standard Lightning Node).
4.  Bob pays the Lightning invoice with his node.
5.  Upon successful payment, the Lightning Network reveals the secret pre-image to Bob.
6.  Bob uses the pre-image to unlock Alice's eCash.

This constitutes a perfect **Atomic Swap**: Bob only gets the eCash if he successfully pays the invoice. Neither party has to trust the other.
