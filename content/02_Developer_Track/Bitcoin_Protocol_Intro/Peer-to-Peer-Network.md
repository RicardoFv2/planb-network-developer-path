---
tags: [bitcoin-core, p2p, networking, developer-track]
title: Peer to Peer Network
---

# Peer-to-Peer Network

[[02_Developer_Track/index-MOC#lecture-01|← Return to Index]]

> [!abstract] TL;DR
> The Bitcoin P2P network is the communication layer where nodes find each other, exchange block headers, and relay transactions. It distinguishes between raw connectivity (`net.cpp`) and high-level message logic (`net_processing.cpp`).

## Viewing Connections

Node operators can view their current peer connections using command-line arguments like `netinfo` via RPC. This provides a dashboard showing inbound and outbound peers, connection types (e.g., Tor, I2P, CJDNS, IPv4/v6), supported service flags, ping times, and data transferred.

## Core Networking Files

Networking logic in Bitcoin Core is conceptually divided into two primary files:

1. **`net.cpp` (Lower Level)**
   - Manages socket connections.
   - Handles the discovery, connecting, and disconnecting of peers.
   - Manages connection limits, banning misbehaving peers (score-based), and basic socket read/write loops.

2. **`net_processing.cpp` (Higher Level Messages)**
   - Contains the high-level logic for parsing the P2P messages once a connection is established.
   - Its core is a massive function named `ProcessMessage()`.
   - It interprets message types like:
     - `VERSION` / `VERACK` (handshakes)
     - `INV` (inventory announcements)
     - `GETDATA` (requesting specific transactions or blocks)
     - `TX` (sending a transaction)
     - `BLOCK` / `CMPCTBLOCK` (sending blocks)

Nodes communicate continuously at high speeds, exchanging inventory data and requesting or forwarding the underlying block and transaction data.

## Related Notes
- [[Bitcoin-Core-Architecture]]
- [[Key-Source-Files]]

[[02_Developer_Track/index-MOC#lecture-01|← Return to Index]]
