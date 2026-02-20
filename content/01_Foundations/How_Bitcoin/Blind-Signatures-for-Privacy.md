---
title: "Blind Signatures for Privacy"
description: "How blind signatures enable private digital cash transactions."
tags:
  - cryptography
  - privacy
  - ecash
---

# Blind Signatures for Privacy

> [!abstract] TL;DR
> Blind signatures allow an authority to sign a piece of data without seeing its content, enabling untraceable digital cash.

## What Is It?

Invented by David Chaum, a blind signature is a form of digital signature in which the content of a message is masked (blinded) before it is signed. The signed message can then be unblinded, resulting in a valid signature for the original message.

## Why Does It Matter?

In a digital cash system, this provides **unlinkability**. The bank signs a "digital coin" but doesn't know the serial number of that specific coin. Therefore, when the coin is eventually spent, the bank cannot link the original depositor to the final spender. This replicates the privacy of physical cash in a digital environment.

## Analogy: The Envelope and Carbon Paper

Imagine a user puts a document and a piece of carbon paper inside an envelope. They give the envelope to an authority. The authority signs the **outside** of the envelope. The pressure of the signature goes through the carbon paper and marks the document inside. The user takes the envelope back, removes the document, and now has a signed document that the authority never actually saw.

## Related Notes

- [[David-Chaum-and-eCash]]
- [[Digital-Signatures-and-Authorship]]
- [[Symmetric-vs-Asymmetric-Cryptography]]

[[index|← Return to Index]]

#cryptography #privacy #ecash #history
