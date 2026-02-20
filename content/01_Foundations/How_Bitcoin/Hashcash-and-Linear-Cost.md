---
title: "Hashcash and Linear Cost"
description: "How Adam Back used Proof of Work to stop spam by making communication costly."
tags:
  - history
  - pow
  - mining
---

# Hashcash and Linear Cost

> [!abstract] TL;DR
> Hashcash introduced Proof of Work to create "digital scarcity" of CPU time, making it expensive to send bulk spam emails.

## What Is It?

Invented by Adam Back in 1997, **Hashcash** was a system designed to limit email spam and denial-of-service attacks. It required the sender to attach a "stamp" to every email. This stamp was a Proof of Work—a hash that met certain criteria (e.g., starting with 20 zeros).

## Why Does It Matter?

- **Linear Cost:** In digital communication, sending 1 message or 1 million messages normally costs nearly the same (**sublinear cost**). Hashcash makes the cost **linear**: to send 1 million messages, you must expend 1 million times the CPU energy.
- **Digital Scarcity:** It proved that you could make "cheap" digital actions "expensive" by anchoring them to physical CPU time and electricity.
- **Foundation of Mining:** Bitcoin uses a modified version of Hashcash as its mining algorithm.

## Significance

Hashcash didn't solve the "double-spend" problem (you could reuse a stamp if the recipient didn't check), but it provided the mechanism for **Proof of Work** that Bitcoin eventually used to secure the Timechain.

## Related Notes

- [[Hal-Finney-and-RPOW]]
- [[Proof-of-Work-Unforgeable-Costliness]]
- [[Satoshi-Nakamoto-The-Final-Synthesis]]

#history #pow #mining #economics
