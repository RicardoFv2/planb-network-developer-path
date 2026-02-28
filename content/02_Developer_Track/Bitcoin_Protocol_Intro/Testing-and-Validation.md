---
tags: [bitcoin-core, testing, validation, developer-track]
title: Testing and Validation
---

# Testing and Validation in Bitcoin Core

[[index|← Return to Index]]

Given that Bitcoin deals with immense monetary value and consensus rules that must remain stable, rigorous testing is a defining characteristic of the codebase development.

## Types of Tests

Bitcoin Core employs several layers of testing:

1. **Unit Tests (C++)**: These are fast-executing tests that verify the internal logic of individual functions and classes in isolation.
2. **Functional Tests (Python)**: These tests behave like a black-box testing framework. They spin up simulated Bitcoin nodes on local networks (`regtest`), issue RPC commands, and observe the end-to-end behavior of the nodes (e.g., verifying that a node correctly handles a specific sequence of blocks or transactions).
3. **Fuzzing (Fuzz Testing)**: This is highly prioritized in Bitcoin Core. Fuzzing involves throwing vast amounts of semi-random, malformed, or unexpected data at functions (especially networking or validation functions) to attempt to trigger undefined behavior, crashes, memory leaks, or stack overflows. The project invests heavily in compute resources for continuous fuzz testing. There's also experimentation with _mutation testing_.

## Avoiding Network Forks

To prevent accidental chain forks, any code that touches the `consensus/` or `kernel/` portions of the repository is subjected to extreme scrutiny.
There is no automated "is this a fork?" test; it relies on:

- Extensive architectural separation (isolating consensus code).
- High review bars for consensus code changes.
- Community vigilance. Accidental forks are thankfully extremely rare due to this rigorous (if slow) human review process.

---

[[index|← Return to Index]]
