---
title: "Merkle Trees and Timestamping"
description: "Efficient data verification and the history of immutable digital timekeeping."
tags:
  - cryptography
  - timechain
  - history
---

# Merkle Trees and Timestamping

[[index|← Return to Index]]

> [!abstract] TL;DR
> Merkle Trees allow efficient verification of large datasets, while timestamping chains create an immutable history of events.

## Merkle Trees (Ralph Merkle)

A Merkle Tree is a data structure that allows for efficient and secure verification of large bodies of data.

- **The Leaves:** Individual data pieces (like transitions).
- **The Branches:** Hashes of the children nodes.
- **The Root:** A single hash (fingerprint) that represents the entire set.
- **Efficiency:** To prove a transaction is in the tree, you only need a few "neighbor" hashes (the Merkle Path). This scales logarithmically ($\log n$).

## The Timestamping Chain (Timeguard)

In the 1990s, companies like **Timeguard** used hashes to prove documents existed at a certain time without revealing their content.

- They would collect document hashes into a Merkle Tree.
- They would publish the **Merkle Root** in the "Public Notices" section of the _New York Times_.
- Because thousands of copies of the newspaper exist worldwide, history became "immutable."

## Bitcoin's Implementation

Bitcoin replaced the _New York Times_ with the **Proof of Work**. Instead of trusting a physical newspaper to publish the root, miners compete to "publish" the root into a block that requires massive energy to create. This creates a chain where each block includes the hash of the previous one.

## Related Notes

- [[Hash-Functions-and-Pre-image-Resistance]]
- [[The-Timechain]]
- [[Proof-of-Work-Unforgeable-Costliness]]

#cryptography #history #timechain #merkletrees
