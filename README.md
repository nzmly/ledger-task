# Ledger / Wallet Service – Assignment

Build a **Ledger / Wallet Service** in **NestJS** with two endpoints:

- `POST /wallet/transaction` → record a new transaction.
- `GET /wallet/transaction` → list all transactions

---

## Requirements

- **Transactions & Ledger**  
  - Record each transaction with `referenceId`, `type`, `amount`, `currency`, and `createdAt`.  
  - Positive amounts increase balance, negative amounts decrease balance.  
  - Balance must **never go negative** (reject if insufficient funds).  
  - All transactions are **append-only** (cannot be updated or deleted).  

- **Currency Handling**  
  - Internally store all amounts in **EGP**.
  - Listing transaction(s) should show original currency

- **Atomicity**  
  - All transactions must be **atomic** (balance should always remain consistent even under concurrent requests).  

- **Idempotency**  
  - If the same `referenceId` is sent more than once, process it **only once**.  

---

## Testing Expectations

Write tests to cover at least:  
- Deposit increases balance.  
- Withdrawal decreases balance and fails if it would go negative.  
- Multiple concurrent transactions keep the balance consistent.  
- Idempotent transaction does not duplicate effects.  

