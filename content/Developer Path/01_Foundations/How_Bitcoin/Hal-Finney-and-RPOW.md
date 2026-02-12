# Hal Finney and RPOW

## Reusable Proof of Work (RPOW)
Created in 2004 by **Hal Finney**, RPOW was a major step towards Bitcoin.

## The Innovation
Adam Back's original Hashcash was "burnt" after one use (to prevent spam). Finney realized that if you could **reuse** and **transfer** those tokens of work, you would have a form of digital money.
- A user creates a PoW token (Hashcash).
- The user sends it to the RPOW server.
- The server creates a new RPOW token, signed and assigned to the user's public key.
- The user can then "spend" this token to another user.

## The Trust Model (Trusted Hardware)
To solve the double-spending problem without a central bank, Finney used **Trusted Platform Modules (TPM)**—specifically specialized IBM chips.
- The RPOW server ran inside a "secure enclave."
- The hardware would sign an attestation proving it was running the correct, un-modified code.
- This meant users didn't have to trust Hal Finney; they only had to trust that the **IBM chip** couldn't be tampered with.

## The Limitation
While it removed the "Issuer" (anyone could create RPOW by doing work), it still had a **Central Mint** (the RPOW server). If the server was shut down or the hardware was backdoored, the system would fail.

---
#history #bitcoin #finney #rpow
