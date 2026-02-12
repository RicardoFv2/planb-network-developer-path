# Blind Signatures for Privacy

## The Problem
If a bank signs a digital banknote for you, they usually know the serial number. When that banknote is later deposited by a merchant, the bank can link your identity to the merchant, destroying your privacy.

## The Solution: Blind Signatures
Invented by **David Chaum**, a blind signature allows an authority to sign a message without ever seeing its content.

## The Envelope Analogy
1. **Preparation:** You write a serial number on a piece of paper and put it in an envelope with a piece of carbon paper.
2. **Blinding:** You give the sealed envelope to the Bank.
3. **Signing:** The Bank signs the *outside* of the envelope. The signature is transferred through the carbon paper onto the serial number inside.
4. **Unblinding:** You take the envelope back and open it. You now have a serial number signed by the bank, but the bank **never saw the number**.

## Mathematical Inception
In cryptography, this is achieved by multiplying the message by a random "blinding factor" before sending it to the signer. After receiving the signature, you divide by the blinding factor to reveal the valid signature on the original message.

## Legacy
Blind signatures are the foundation of **Chaumian Mints**, which are still relevant today in Bitcoin-adjacent technologies like **Fedimint** and **Cashu**.

---
#cryptography #privacy #ecash
