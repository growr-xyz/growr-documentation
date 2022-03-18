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