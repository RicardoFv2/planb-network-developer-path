# Digital Signatures and Authorship

## Overview
While encryption is used to keep secrets, **Digital Signatures** are used to prove who sent a message and that it hasn't been tampered with.

## How it Works
1. **Signing:** The sender uses their **Private Key** to create a mathematical "seal" (signature) on a piece of data.
2. **Verification:** Anyone with the sender's **Public Key** can verify that the signature is valid.
3. **Properties:**
    - **Authenticity:** Only the person with the private key could have created the signature.
    - **Integrity:** If the message is changed even by one bit, the signature becomes invalid.
    - **Non-repudiation:** The sender cannot later deny sending the message.

## The Wax Seal Analogy
In the Middle Ages, a noble would use a signet ring (Private Key) to press a unique emblem into wax. Anyone recognizing the emblem (Public Key) knew the letter was authentic. Replicating the signet ring was hard; recognizing the seal was easy.

## Importance for Bitcoin
Bitcoin transactions are not "encrypted." They are **Publicly Signed**. When you send BTC, you are signing a message that says: *"I, the owner of these funds, authorize their transfer to this new address."*

---
#bitcoin #cryptography #signatures
