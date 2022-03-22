# Credentials Verification
Verifiable credentials are consumed by **Verifiers** using the concepts and data models for **presentation exchange**.   
Below is a standard process for credential verification using a custodial SSFI App to request the verification before applying for a loan. In non-custodial model, the process is the almost the same - instead of SSFI App, the user would use an agent app with connected self-managed wallet. The process follows the same pattern in the cases when credentials of other protocol participants (eg. Lenders and Liquidity providers) must be verified.  
```mermaid
sequenceDiagram
    participant Borrower (Subject)
    participant SSFI App
    participant Credential Verifier
    participant Trusted Registries
    Note over SSFI App: Custodial Distributor App or Self-managed wallet
    Borrower (Subject)->>SSFI App: Request credentials verification
    activate SSFI App
    SSFI App->>Borrower (Subject): Select credentials
    SSFI App->>SSFI App: Build and sign credential presentation
    SSFI App->>Credential Verifier: Send credential presentation
    activate Credential Verifier
    opt
        Credential Verifier->>Trusted Registries: Check in Trusted Issuers registry
        Credential Verifier->>Trusted Registries: Check in Status registry
    end
    Credential Verifier->>Credential Verifier: Verify credentials
    alt If OK?
        opt
            Credential Verifier->>Credential Verifier: Build & sign verification result
            Credential Verifier->>Trusted Registries: Store verification result in registry
        end
        Credential Verifier->>SSFI App: Credential verified
        Note left of Credential Verifier: (Optionally) Send verification result
        SSFI App-->>Borrower (Subject): "Verified credential"
    else If not OK
        Credential Verifier->>SSFI App: Verification failed
        SSFI App-->>Borrower (Subject): "Invalid credential"
    end
    deactivate Credential Verifier
    deactivate SSFI App
```
The credential verification performed by the Verifier includes the following tasks:  
- Verify that the credential presentation is signed with the Subject's SSFI
- Verify that the credential is signed by a trusted Issuer
- Verify that the credential is not expired
- Verify that the credential is not revoked  
This verification process is part of the overall loan approval process. For more details, see [Loan Approval section](./C-Risk-Mgmt-3-Loan-Approval.md).
