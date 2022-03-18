```mermaid
sequenceDiagram
    participant Lender (via dApp)
    participant Pond Factory SC
    activate Lender (via dApp)
    opt optional
        Lender (via dApp)->>Verification Registry SC: Create Verification Registry SC
        Note left of Verification Registry SC: Lender might rely on existing registry
        loop
            Lender (via dApp)->>+Verification Registry SC: Add/remove trusted verifier(s)
            Verification Registry SC->>-Lender (via dApp): "Registered verifier"
        end
    end
    Lender (via dApp)->>+Pond Factory SC: Request pond creation
    Note right of Lender (via dApp): Provide parameters, eligibility criteria, VR address
    Pond Factory SC->>Pond Factory SC: Validate parameters
    Pond Factory SC->>Pond SC: Create pond
    Pond Factory SC-->>-Lender (via dApp): "Pond address"
    loop
        Lender (via dApp)->>Pond SC: Deposit funds
    end
    deactivate Lender (via dApp)
    ```