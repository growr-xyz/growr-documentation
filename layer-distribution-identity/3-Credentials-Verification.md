# Credentials Verification
Below is a standard process for credential verification using a custodial distribution app to request the verification before applying for a loan. In non-custodial model, the process is the almost the same - instead of custodial distribution app, the user would use a dApp with connected self-custody wallet. The process follows the same pattern in the cases when credentials of other protocol participants (eg. Lenders and Liquidity providers) must be verified.  
```mermaid
sequenceDiagram
    participant Borrower (Subject)
    participant Borrowing App
    participant Credential Verifier
    participant Trusted Service Registry SC
    participant Credential Status Registry SC
    Note over Borrowing App: Custodial distribution app or Self-custody wallet
    Borrower (Subject)->>Borrowing App: Request credentials verification
    activate Borrowing App
    Borrowing App->>Borrower (Subject): Select credentials
    Borrowing App->>Borrowing App: Build and sign credential presentation
    Borrowing App->>Credential Verifier: Send credential presentation
    activate Credential Verifier
    Credential Verifier->>Trusted Service Registry SC: Check issuer
    opt  
        Credential Verifier->>Credential Status Registry SC: Check status
    end
    Credential Verifier->>Credential Verifier: Verify credentials
    alt If OK?
        Credential Verifier->>Credential Verifier: Build & sign verification result
        Note right of Credential Verifier: Optionally, the result can be persisted in a registry
        Credential Verifier->>Borrowing App: Verification result
        Borrowing App-->>Borrower (Subject): "Verified credential"
    else If not OK
        Credential Verifier->>Borrowing App: Verification failed
        Borrowing App-->>Borrower (Subject): "Invalid credential"
    end
    deactivate Credential Verifier
    deactivate Borrowing App
```
The credential verification performed by the Verifier includes the following tasks:
- Verify that the credential presentation is signed with the Subject's SSFI
- Verify that the credential is signed by a trusted Issuer
- Verify that the credential is not expired
- Verify that the credential is not revoked

This verification process is part of the overall loan approval process. For more details, see [Loan Approval section](../layer-risk/2-Loan-Approval.md).
