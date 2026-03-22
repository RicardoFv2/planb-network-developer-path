---
title: Cashu Mint Architecture
aliases: [Cashu Server, Mint Custodian]
tags: [architecture, cashu, mint, privacy, security]
---
# Cashu Mint Architecture

[[02_Developer_Track/index-MOC#lecture-04|← Return to Index]]

> [!abstract] TL;DR
> A Cashu mint is a central server that manages token issuance and double-spend prevention. Due to blind signatures, the mint never sees which user is spending which token.

## Custodial, but Private
The Cashu Mint is conceptually similar to a bank or a PayPal server in that it **holds custody of the funds (Bitcoin via Lightning)** backing the eCash it issues. 

However, because the protocol utilizes [[02_Developer_Track/Cashu_and_Ecash/Blind-Signatures-Cryptography|Blind Signatures]], the central server lacks the capacity to monitor or track user balances. 

### The Mint's Perspective
From the Mint's standpoint, a transaction involves:
1. Receiving a blinded string of text (`B'`) from an anonymous IP address.
2. Mathematically signing the string and handing it back.
3. Later, receiving a completely different-looking (unblinded) string (`x`) along with a valid signature.
4. Verifying against a database to ensure `x` hasn't been redeemed before.
5. Deleting `x` from circulation and issuing a new blinded token.

The Mint cannot link the "deposit" (the blinding process in step 1/2) to the "withdrawal" (the unblinding and redemption process in step 3/4). Thus, it has zero insight into sender-receiver relationships or user wealth.

## The Mint's Database
The mint's primary computational and storage burden is maintaining the double-spend database. 
Unlike the massive, ever-growing Bitcoin blockchain, the mint only needs to store a simple database of the secret values (`x`) that have *already been spent*. 

Once an eCash token is sent back to the mint for redemption, the mint records `x` in its "spent" database. If anyone submits `x` again in the future, the mint rejects the transaction.

## Single Mint vs. Multi-Mint Architecture
A single mint is incredibly scalable; a standard server can easily support tens of thousands of concurrent users because eCash operations are extremely lightweight compared to Lightning nodes.

However, because mints are custodial, they carry "hot wallet" risk. Users are advised to:
*   Treat eCash like physical cash inside an untrusted wallet. DOn't store life savings on them.
*   **Diversify Across Mints**: Cashu wallets automatically support spreading a user's balance across dozens of different, independently-operated mints entirely seamlessly. If one mint goes offline or acts maliciously, the risk is contained to a fraction of the user's total active capital.

## Deep Irreversibility 
Though the mint runs as a centralized server, the eCash ecosystem maintains strong censorship resistance through mathematical irreversibility. 
Because the mint cannot predict the future unblinded state of a token it issues, it is entirely incapable of freezing funds, blocking transactions, or seizing specific eCash tokens once they have left its server. The only action a malicious mint can take is collectively stealing the underlying Bitcoin lighting liquidity, which is why users distribute risk across multiple mints.
