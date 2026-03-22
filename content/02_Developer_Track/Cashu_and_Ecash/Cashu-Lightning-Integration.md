---
title: Cashu Lightning Integration
aliases: [Lightning Mints, Minting and Melting]
tags: [lightning, cashu, interoperability, payments]
---
# Cashu Lightning Integration

[[02_Developer_Track/index-MOC#lecture-04|← Return to Index]]

> [!abstract] TL;DR
> Cashu uses the Lightning Network as its "connective tissue," allowing users to "mint" eCash by paying Lightning invoices and "melt" eCash to settle invoices.
 

Cashu uses the Lightning Network as the connective tissue bridging independent eCash mints directly to the broader global Bitcoin economy. 

Within a specific mint, eCash tokens are transferred peer-to-peer outside the bounds of any network. However, to cross between mints or interact with non-eCash actors, Cashu relies on the process of **Minting** and **Melting**.

## 1. Minting (LN -> eCash)
"Minting" is the process of generating new eCash by funding the mint with Bitcoin via the Lightning Network.

1.  A user asks the mint to generate a Lightning invoice for a specific amount (e.g., 200 sats).
2.  The user (or someone else) pays that invoice using any standard Lightning wallet.
3.  Once the mint detects the invoice is settled, the user submits 200 sats worth of blinded secrets.
4.  The mint signs the secrets, giving the user 200 sats of valid eCash.

In this flow, the user effectively "bought" anonymized eCash tokens utilizing an anonymous Lightning payment.

## 2. Melting (eCash -> LN)
"Melting" is the reverse process, destroying eCash to fulfill a Lightning payment.

1.  A user receives a Lightning invoice from a merchant.
2.  The user sends the invoice to their Cashu Mint, along with enough eCash tokens to cover the cost (plus any routing fees).
3.  The mint marks those eCash tokens as spent (melting them) and promptly pays the invoice via its own Lightning node.
4.  If the Lightning payment fails, the mint returns the eCash tokens to the user.

## Inter-Mint Connectivity
Because all mints essentially function as Lightning custodial nodes acting on behalf of their users, this creates a seamlessly interconnected ecosystem.

If Alice (using Mint A) wants to pay Bob (using Mint B):
1. Bob requests 100 sats of eCash from Mint B, generating an invoice.
2. Bob sends the invoice to Alice.
3. Alice melts 100 sats of her eCash on Mint A to pay Bob's invoice.
4. Mint A settles the Lightning invoice to Mint B.
5. Mint B issues 100 sats of eCash to Bob.

From a UX perspective, this abstracts away network complexities. The users just scan codes and pay, regardless of which mints they operate on. This horizontal scalability allows the network to grow infinitely without increasing friction.
