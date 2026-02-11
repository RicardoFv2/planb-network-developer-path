# E-Cash Flow and Double-Spending Diagram

## The Centralized E-Cash Flow (Chaumian)
This diagram illustrates how digital cash worked before Bitcoin, highlighting the role of the central mint and the blind signature process.

```mermaid
sequenceDiagram
    participant User as User (Alice)
    participant Bank as Central Bank/Mint
    participant Merchant as Merchant (Bob)

    Note over User: 1. Generates Serial Number
    Note over User: 2. "Blinds" the Number
    User->>Bank: Request Withdrawal (Blind Message)
    Note over Bank: 3. Signs Blinded Message
    Bank-->>User: Blinded Signature
    Note over User: 4. "Unblinds" (Reveals valid signature)
    
    User->>Merchant: 5. Sends Signed Serial Number (Payment)
    Merchant->>Bank: 6. "Is this Serial Number spent?"
    
    alt Not Spent
        Bank-->>Merchant: 7. Valid. Funds credited.
        Note over Bank: Marks Serial Number as "Spent"
        Merchant-->>User: Delivers Good/Service
    else Already Spent (Double-Spend)
        Bank-->>Merchant: 7. REJECTED! Already spent.
        Note over Merchant: Transaction Fails
    end
```

## Transition to Bitcoin
The primary difference is that in Bitcoin, the **"Bank/Mint"** is replaced by a **Decentralized Network of Nodes** and the **Blockchain**.

---
#diagram #bitcoin #ecash
