# Loan Offer
## Custodial Model
### Pond Factory holding pond details
TBD-description
```mermaid
sequenceDiagram
    participant Borrower
    participant Distributor App
    participant Pond Factory SC
    Note over Borrower: Borrower has SSI and credentials
    Borrower->>Distributor App: Apply for loan
    activate Distributor App
    Distributor App->>Pond Factory SC: Request loan offers
    activate Pond Factory SC
    Pond Factory SC->>Distributor App: Provide loan offers
    deactivate Pond Factory SC
    Distributor App->>Distributor App: Compare offers
    Distributor App->>Borrower: Provide loan parameters
    deactivate Distributor App
```
TBD-description
### Pond Factory holding only pond addresses
TBD-description
```mermaid
sequenceDiagram
    participant Borrower
    participant Distributor App
    participant Pond Factory SC
    participant Pond SC
    Note over Borrower: Borrower has SSI and credentials
    Borrower->>Distributor App: Apply for loan
    activate Distributor App
    Distributor App->>Pond Factory SC: Request pond list
    activate Pond Factory SC
    Pond Factory SC-->>Distributor App: Provide pond list
    deactivate Pond Factory SC
    loop Get offers from ponds
        Distributor App->>Pond SC: Request pond details
        activate Pond SC
        Pond SC->>Pond SC: Check eligibility
        Pond SC-->>Distributor App: Provide approval & loan parameters
        deactivate Pond SC
    end
    Distributor App->>Distributor App: Compare offers
    Distributor App->>Borrower: Provide loan parameters
    deactivate Distributor App
```
TBD-description
## Non-Custodial Model
TBD-description