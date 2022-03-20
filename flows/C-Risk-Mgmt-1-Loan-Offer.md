# Loan Offer
## Custodial Model
In a custodial model, the Borrowers requests a loan offer from the protocol using a custodial mobile or web application. There are 2 scenarios for loan offering, depending on the implementation of the Pond Factory smart contract.
### Pond Factory holding pond details
In this first scenario, the Pond Factory smart contract holds the details of all ponds created from its invocation requests.
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
### Pond Factory holding only pond addresses
In this second scenario, the Pond Factory smart contract holds only a list of addresses of the ponds created from its invocation requests and the Distributor App must "ask" for details each individual pond.
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
## Non-Custodial Model
The non-custodial loan offer flow is almost the same. The main difference is that instead of Distributor App, the borrower would use an agent app with connected self-managed wallet.
