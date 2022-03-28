# Loan Offering
In a custodial model, the Borrowers requests a loan offer from the protocol using a custodial mobile or web application. The non-custodial loan offer flow is almost the same. The main difference is that instead of custodial app, the borrower would use a dApp with connected self-custody wallet.  
There are different scenarios for loan offering, depending on the protocol implementation, and in particular - where the pond details are stored (cached).
In scenario below, the Pond Factory smart contract holds only a list of addresses of the ponds created from its invocation requests and the Borrowing App must "ask" for details each individual pond.
```mermaid
sequenceDiagram
    participant Borrower
    participant Borrowing App
    participant Pond Factory SC
    participant Pond SC
    Note over Borrower: Borrower has credentials
    Borrower->>Borrowing App: Apply for loan
    activate Borrowing App
    Borrowing App->>Pond Factory SC: Request pond list
    activate Pond Factory SC
    Pond Factory SC-->>Borrowing App: Provide pond list
    deactivate Pond Factory SC
    loop Get offers from ponds
        Borrowing App->>Pond SC: Request pond details
        activate Pond SC
        Pond SC->>Pond SC: Check eligibility
        Pond SC-->>Borrowing App: Provide approval & loan parameters
        deactivate Pond SC
    end
    Borrowing App->>Borrowing App: Compare offers
    Borrowing App->>Borrower: Provide loan parameters
    deactivate Borrowing App
```
