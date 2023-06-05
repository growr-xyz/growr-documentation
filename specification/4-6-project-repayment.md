## Project repayment

### Project repayment with a bank account

```mermaid
sequenceDiagram
  actor o as Originator
  participant lp as Lending portal
  participant fs as Growr Funding service
  actor i as Investor

  o->>i: Make wire transfer
  o->>+lp: Register repayment
  lp->>+fs: Register repayment
  fs->>fs: Create a record
  fs-->>-lp: Confirmation
  lp-->>-o: Confirmation
```

Process steps:

1. According to the agreed repayment plan, an originator makes a wire transfer to the bank account of the investor.
2. The originator also registers the repayment through the Lending portal.
3. The Lending portal sends the information to the Growr Funding service.
4. Growr Funding service creates a new record in the Funding book.
5. Response message.
6. Response message.

### Project repayment with an on-chain wallet

```mermaid
sequenceDiagram
  actor o as Oritinagor
  participant pw as Originator wallet
  participant btc as Bitcoin network
  participant bs as Growr Bitcoin service
  participant fs as Growr Funding service
  participant iw as Investor wallet

  o->>+pw: Sign transaction
  pw->>-btc: Send transaction
  activate btc
  btc->>btc: Confirm transaction
  btc->>-iw: Transfer amount
  bs->>btc: Detect transaction
  activate bs
  bs->>-fs: Register repayment
  activate fs
  fs->>fs: Create a record
  fs-->>-o: Confirmation
```

Process steps:

1. An originator signs an on-chain transaction using his Bitcoin wallet.
2. The originator's wallet sends the transaction to the Bitcoin network.
3. The transaction is confirmed by the network in the next block.
4. The amount is transferred to the Bitcoin wallet address of the investor.
5. Growr Bitcoin service detects the outgoing transaction.
6. Growr Bitcoin service sends the information to the Growr Funding service.
7. Growr Funding service creates a new record in the Funding book.
8. Response message.

<div style="page-break-after: always;"></div>
