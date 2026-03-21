---
title: "Breeze Noster Integration (NWC)"
description: "Bridging the Bitcoin SDK with the Noster protocol for Zaps and remote wallet control."
tags:
  - developer-track
  - noster
  - nwc
  - zaps
---

# Breeze Noster Integration (NWC)

[[02_Developer_Track/index|← Return to Index]]

> [!abstract] Core Concept
> The Breeze SDK supports **Noster Wallet Connect (NWC)**, a protocol that allows a Noster application (like Damos or Primal) to remotely communicate with a user’s wallet to request invoices or send "Zaps."

## ⚡ What are Zaps?
In the Noster ecosystem, a "Zap" is a micro-payment sent to a content creator as a form of "like" or tip. The SDK facilitates this by:
1. Receiving a request from a Noster client.
2. Generating a Lightning invoice or paying one automatically if balance allows.
3. Broadcasting the "Zap Note" to the Noster relays.

## 🔌 NWC: Remote Control
NWC allows you to link your mobile wallet (running the Breeze SDK) to a web browser or desktop app via a secure encrypted relay.
- **Permissions:** You can set limits (e.g., "Allow this app to spend up to 1,000 SATs per day").
- **Encrypted Communication:** The SDK and the Noster app communicate using asymmetric encryption over Noster relays.
- **Zero Configuration:** The user simply scans a QR code to authorize the connection.

## 🏗️ Implementation for Developers
For a developer building a Noster app, the Breeze SDK acts as the "Backend" wallet support. You don't need to build a wallet; you just call the NWC methods to interact with the user's existing funds.

## 🌐 The Vision: A Seamless Web
Breeze's support for NWC is a step toward "Lightning in every app," where social media, gaming, and content platforms can handle money without ever holding user keys.

---

**References:**
- [[02_Developer_Track/03. Liquid SDK & Breeze - Deep Dive Summary|03. Liquid SDK & Breeze - Deep Dive Summary]]
