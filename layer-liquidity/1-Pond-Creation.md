# Pond Creation

## Pond Creation
Below is a diagram that illustrates the steps for creation of a lending pond.
```mermaid
sequenceDiagram
    participant Lender
    participant Lending App
    participant Pond Factory SC
    participant Trusted Service Registry SC
    Lender->>Lending App: Initiate pond creation
    activate Lending App
    opt optional
        Lending App->>Trusted Service Registry SC: Create Trusted Service Registry SC
        Note left of Trusted Service Registry SC: Lender might rely on existing registry
        loop
            Lending App->>+Trusted Service Registry SC: Add/remove trusted Verifier(s)
            Trusted Service Registry SC->>-Lending App: "Registered Verifier"
        end
    end
    Lending App->>+Pond Factory SC: Request pond creation
    Note right of Lending App: Provide parameters, eligibility criteria, VR address
    Pond Factory SC->>Pond Factory SC: Validate parameters
    Pond Factory SC->>Pond SC: Create pond
    Pond Factory SC-->>-Lending App: "Pond address"
    Lending App-->>Lender: "Pond created"
    deactivate Lending App
    loop
        Lender->>Pond SC: Deposit funds
        Note right of Lender: See: Pond funding
    end
```
The parameters for pond creation includes:
- Owner
- Name
- Currency/Token
- Min & max loan amount
- Min & max loan duration
- Annual interest rate
- Disbursement fee
- Cash-back rate
- Strict eligibility criteria
- Reserve requirements
- Trusted Service Registry address

Once created, pond parameters cannot be changed. If the pond owner wants to modify certain parameters, they would create a new pond.

An important parameter of every pond is the configured address of Trusted Service Registry smart contract. The pond will rely on this smart contract to validate that the eligibility check was performed by a trusted Risk Assessor. Trusted Service Registry contracts can be created either by pond owners or by the protocol governance body (recommended).  
The protocol envisions a possibility for the owner to stop or pause the lending from a pond i.e. to permanently or temporary block future loan approvals from a pond.

## Pool Creation
The flow for pool creation is very similar to the flow for pond creation:
```mermaid
sequenceDiagram
    participant Liquidity Provider
    participant Lending App
    participant Pool Factory SC
    Liquidity Provider->>Lending App: Initiate Pool creation
    activate Lending App
    Lending App->>+Pool Factory SC: Request Pool creation
    Note right of Lending App: Provide parameters
    Pool Factory SC->>Pool Factory SC: Validate parameters
    Pool Factory SC->>Pool SC: Create Pool
    Pool Factory SC-->>-Lending App: "Pool address"
    Lending App-->>Liquidity Provider: "Pool created"
    deactivate Lending App
    loop
        Lender->>Pool SC: Deposit funds
        Note right of Lender: See: Pond funding
    end
```
The parameters for pond creation includes:
- Owner
- Name
- Currency/Token
- Min & max credit limit
- Annual interest rate
- Reserve requirements