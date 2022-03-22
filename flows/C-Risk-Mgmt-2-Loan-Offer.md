# Loan Offer
In a custodial model, the Borrowers requests a loan offer from the protocol using a custodial mobile or web application. The non-custodial loan offer flow is almost the same. The main difference is that instead of SSFI App, the borrower would use an agent app with connected self-managed wallet.  
There are 2 scenarios for loan offering, depending on the implementation of the Pond Factory smart contract.  
## Pond Factory holding pond details
In this first scenario, the Pond Factory smart contract holds the details of all ponds created from its invocation requests.
```mermaid
sequenceDiagram
    participant Borrower
    participant SSFI App
    participant Pond Factory SC
    Note over SSFI App: Custodial Distributor App or Self-managed wallet
    Note over Borrower: Borrower has credentials
    Borrower->>SSFI App: Apply for loan
    activate SSFI App
    SSFI App->>Pond Factory SC: Request loan offers
    activate Pond Factory SC
    Pond Factory SC->>SSFI App: Provide loan offers
    deactivate Pond Factory SC
    SSFI App->>SSFI App: Compare offers
    SSFI App->>Borrower: Provide loan parameters
    deactivate SSFI App
```
## Pond Factory holding only pond addresses
In this second scenario, the Pond Factory smart contract holds only a list of addresses of the ponds created from its invocation requests and the SSFI App must "ask" for details each individual pond.
```mermaid
sequenceDiagram
    participant Borrower
    participant SSFI App
    participant Pond Factory SC
    participant Pond SC
    Note over SSFI App: Custodial Distributor App or Self-managed wallet
    Note over Borrower: Borrower has credentials
    Borrower->>SSFI App: Apply for loan
    activate SSFI App
    SSFI App->>Pond Factory SC: Request pond list
    activate Pond Factory SC
    Pond Factory SC-->>SSFI App: Provide pond list
    deactivate Pond Factory SC
    loop Get offers from ponds
        SSFI App->>Pond SC: Request pond details
        activate Pond SC
        Pond SC->>Pond SC: Check eligibility
        Pond SC-->>SSFI App: Provide approval & loan parameters
        deactivate Pond SC
    end
    SSFI App->>SSFI App: Compare offers
    SSFI App->>Borrower: Provide loan parameters
    deactivate SSFI App
```
