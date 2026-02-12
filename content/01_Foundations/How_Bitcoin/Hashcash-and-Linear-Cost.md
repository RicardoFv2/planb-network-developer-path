# Hashcash and Linear Cost

## The Problem: Sublinear Cost
In the digital world, sending 1 email has a fixed cost (computer, internet, time). However, sending 1,000,000 emails costs almost exactly the same as sending one. This **sublinear cost** is what makes spam possible.

## The Solution: Hashcash (Adam Back, 1997)
Adam Back proposed a system where a computer must perform a small amount of work before sending an email.
- **The Task:** Find a "partial collision" in a hash function (e.g., a SHA-256 hash that starts with 20 zeros).
- **Verification:** The receiver's computer can check the work instantly (one hash), but the sender's computer had to try millions of combinations to find it.

## Why it Works: Linear Cost
Unlike a simple digital copy, Proof of Work (PoW) is **non-copyable**.
- If you change the recipient's name or the timestamp, the hash changes completely.
- This forces the sender to perform the work again for every single email.
- **1 Email = 1 Unit of Work.**
- **1 Million Emails = 1 Million Units of Work.**

## Significance for Bitcoin
Satoshi Nakamoto used Hashcash as the engine for Bitcoin's **Proof of Work**. It is what prevents attackers from "spamming" the network with fake blocks or rewriting history.

---
#bitcoin #mining #hashcash #spam
