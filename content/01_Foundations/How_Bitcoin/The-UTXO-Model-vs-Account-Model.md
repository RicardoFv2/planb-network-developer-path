# The UTXO Model vs. Account Model

## Account Model (The Bank Approach)
- **Used by:** Traditional banks, PayPal, Ethereum.
- **Logic:** Each user has an "account" with a balance (e.g., $100). When a transaction happens, the system subtracts from one balance and adds to another.
- **Analogy:** A whiteboard where names and totals are written and erased.
- **Privacy:** Poor. The identity is tied directly to the balance.

## UTXO Model (The Cash Approach)
- **Used by:** Bitcoin.
- **Logic:** There are no "accounts" or "balances." There are only **Unspent Transaction Outputs (UTXOs)**.
- **Analogy:** A wallet full of physical banknotes of different denominations ($5, $20, $50).
- **How it works:**
    - To pay $15, you might use a $20 UTXO (Input).
    - The transaction creates two new UTXOs (Outputs): $15 for the merchant and $5 back to you as "change."
- **Privacy:** Better. You can use a different "address" for every single UTXO, making it harder to track total wealth.

## Advantages of UTXO
1. **Parallelism:** Transactions can be processed in parallel because they don't depend on a single account state.
2. **Scalability:** It is easier to verify the "history" of a specific piece of money.
3. **Privacy:** Encourages the use of single-use addresses.

---
#bitcoin #protocol #utxo
