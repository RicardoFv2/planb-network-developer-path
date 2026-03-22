---
tags: [bitcoin-core, architecture, developer-track]
title: Bitcoin Core Architecture
---

# Bitcoin Core Architecture

[[02_Developer_Track/index-MOC#lecture-01|← Return to Index]]

> [!abstract] TL;DR
> Bitcoin Core is the reference implementation of the Bitcoin protocol, primarily written in C++. Its architecture emphasizes a headless daemon (`bitcoind`) for consensus and networking, supported by various CLI and GUI utilities.

## Core Components

The `src/` directory contains the main components of the Bitcoin Core software:

- **bitcoind**: The headless daemon that runs the node. It handles the peer-to-peer network, maintains the blockchain, and provides an RPC interface.
- **bitcoin-qt**: The graphical user interface (GUI) version of the node. Currently moving towards a QML-based interface rather than the old Qt one.
- **bitcoin-cli**: A command-line interface tool used to send RPC commands to `bitcoind`.
- **bitcoin-tx**: A utility to create, parse, and modify transactions without needing to run a full node or interact with the wallet.
- **bitcoin-wallet**: A tool for managing the wallet database without running a node.

The architecture emphasizes separation of concerns where possible, though much legacy code remains. Significant effort is ongoing to separate consensus-critical code into its own specific module (`libbitcoinkernel`), isolating it from networking, wallet, or RPC components.

## Related Notes
- [[Key-Source-Files]]
- [[Building-Bitcoin-Core]]

[[02_Developer_Track/index-MOC#lecture-01|← Return to Index]]
