---
title: "Bitcoin Script & OpCodes"
description: "Understanding the stack-based execution environment behind Bitcoin smart contracts."
tags:
  - developer-track
  - script
  - smart-contracts
---

# Bitcoin Script & OpCodes

[[02_Developer_Track/index-MOC#lecture-02|← Return to Index]]

> [!abstract] TL;DR
> Bitcoin Script is a stack-based, non-Turing complete language that defines how UTXOs can be spent. OpCodes like `OP_HASH160` and `OP_CHECKLOCKTIMEVERIFY` are the building blocks of smart contracts and HTLCs.

## The Stack-Based Machine
When evaluating a Bitcoin transaction, the interpreter pushes parameters (like signatures and public keys) onto a stack and then executes operations step-by-step. If at the end of the execution the script returns `True` without encountering any errors, the funds can be spent.

## Key HTLC OpCodes
In the context of Hash Time Locked Contracts (HTLCs) for swaps, the script validates branches using specific instructions:

- `OP_SIZE`: Inspects the size of the top element on the stack (used to ensure preimages are exactly 32 bytes to prevent vulnerabilities).
- `OP_HASH160`: Hashes the top element on the stack using SHA-256 followed by RIPEMD-160.
- `OP_EQUALVERIFY`: Compares the top two items on the stack. If they are not equal, the script terminates with an error (false). If they match, they are consumed and execution continues.
- `OP_CHECKSIG`: Validates a cryptographic signature against a public key and the transaction data.
- `OP_CHECKLOCKTIMEVERIFY` (`OP_CLTV`): Ensures that a specific absolute block height or Unix timestamp has passed before allowing the transaction to be included in a block.

By combining these building blocks with conditional logic (`OP_IF` / `OP_ELSE`), developers create complex locking scripts that power Lightning channels, Submarine Swaps, and other layer-two constructs.

---

**References:**
- [[02_Developer_Track/02. Technical Part (Swaps & Layers) - Deep Dive Summary|02. Technical Part (Swaps & Layers) - Deep Dive Summary]]
