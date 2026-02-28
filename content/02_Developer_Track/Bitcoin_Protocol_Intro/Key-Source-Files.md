---
tags: [bitcoin-core, source-code, developer-track]
title: Key Source Files
---

# Key Source Files in Bitcoin Core

[[index|← Return to Index]]

The `src/` directory in the Bitcoin Core repository contains the C++ files that power the node. Here are a few of the most important files any new contributor should become familiar with:

## Initialization and Main Loop

- **`init.cpp`**: The primary initialization file. It parses command-line arguments, reads `bitcoin.conf`, sets up logging, initializes state variables, starts background threads, and orchestrates the startup sequence of the node.
- **`bitcoind.cpp`**: The specific entry point (main function) for the `bitcoind` headless executable.

## Validation and Consensus

- **`validation.cpp`** (and **`validation.h`**): This is arguably the most critical file. It contains the logic for validating transactions (e.g., `AcceptToMemoryPool`) and validating blocks (`CheckBlock` and `ConnectBlock`). `ConnectBlock` is where the heavy context-dependent consensus checks reside.
- **`consensus/` folder**: Contains code purely related to Bitcoin consensus rules (the rules all nodes must agree on to stay on the same chain).

## Peer-to-Peer Networking

- **`net.cpp`**: Handles the lower-level socket connections to peers. It deals with finding nodes, maintaining connections, socket handlers, and banning misbehaving peers.
- **`net_processing.cpp`**: Contains the higher-level logic. It implements the function `ProcessMessage()`, interpreting individual P2P messages (like `GETDATA`, `INV`, `TX`, `BLOCK`) exchanged between nodes.

## Mempool

- **`txmempool.cpp`**: Manages the memory pool, storing unconfirmed transactions waiting to be included in a block. Nodes can implement unique policies (different from consensus) regarding what they accept into their own mempool.

---

[[index|← Return to Index]]
