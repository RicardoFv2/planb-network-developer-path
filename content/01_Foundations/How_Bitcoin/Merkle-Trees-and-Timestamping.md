# Merkle Trees and Timestamping

## Merkle Trees (Ralph Merkle)
A Merkle Tree is a data structure that allows for efficient and secure verification of large bodies of data.
- **The Leaves:** Individual data pieces (like transactions).
- **The Branches:** Hashes of the children nodes.
- **The Root:** A single hash that represents the entire set.
- **Verification:** To prove a transaction is in the tree, you only need a few "neighbor" hashes (the Merkle Path). This scales logarithmically ($\log n$).

## The Timestamping Chain (Timeguard)
In the 1990s, companies like **Timeguard** used hashes to prove documents existed at a certain time without revealing their content.
- They would collect thousands of document hashes into a Merkle Tree.
- They would take the **Merkle Root** and publish it in the "Public Notices" section of a physical newspaper (like the *New York Times*).
- Because thousands of copies of the newspaper exist worldwide, history became "immutable." You couldn't change the hash without finding and destroying every physical newspaper in existence.

## Linking the Chain
Timeguard took it a step further by including the **previous day's hash** in the current day's root. This created a **Chain of Hashes**.

## Bitcoin's Implementation
Bitcoin replaced the *New York Times* with the **Proof of Work**. Instead of trusting a newspaper to publish the root, miners compete to "publish" the root into a block that requires massive energy to create.

---
#cryptography #bitcoin #merkletrees #timestamping
