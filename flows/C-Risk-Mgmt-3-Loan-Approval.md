# Loan Approval
## Custodial Model
TBD-description
```mermaid
sequenceDiagram
    participant Borrower
    participant Distributor App
    participant Risk Assessor
    participant Pond SC
    participant Verification Registry SC
    Note over Borrower: ...Borrower has credentials and loan offer
    Borrower->>Distributor App: Accept loan offer
    activate Distributor App
    Distributor App->>Distributor App: Create credential presentation
    Distributor App->>Risk Assessor: Request loan risk assessment
    activate Risk Assessor
    Note right of Distributor App: Provide credentials
    Risk Assessor->>Pond SC: Get loan requirements
    Risk Assessor->>Risk Assessor: Verify credentials
    alt credentials not OK?
        Risk Assessor-->>Distributor App: Failed verification
        Distributor App-->>Borrower: "Verification failed"
    end
    opt optional
        Risk Assessor->>Risk Assessor: Request loan application review
        Note right of Risk Assessor: Manual review
    end
    opt optional
        Risk Assessor->>Risk Assessor: Calculate risk score
        Note right of Risk Assessor: Via risk engine module
    end
    Risk Assessor->>Risk Assessor: Validate eligibility
    alt requirements not met?
        Risk Assessor-->>Distributor App: Failed eligibility check
        Distributor App-->>Borrower: "Not eligible for the loan"
    end
    Risk Assessor->>Risk Assessor: Issue & sign verification result
    Risk Assessor-->>Distributor App: Return verification result
    Note right of Risk Assessor: Result is not stored on-chain!
    deactivate Risk Assessor
    Distributor App->>Pond SC: Apply for loan
    activate Pond SC
    Note right of Distributor App: Provide verification result
    Pond SC->>Verification Registry SC: Send verification result
    activate Verification Registry SC
    Verification Registry SC->>Verification Registry SC: Validate verifier
    Verification Registry SC-->>Pond SC: Validation result
    deactivate Verification Registry SC
    alt result not OK?
        Pond SC-->>Distributor App: Loan rejected
        Distributor App-->>Borrower: "Loan rejected"
    else result OK?
        Pond SC->>Pond SC: Approve loan & register on-chain
        opt
            Note over Pond SC: Loan disbursement...
        end
        Pond SC-->>Distributor App: Loan approvedx
        Distributor App-->>Borrower: "Loan approved"
    end
    deactivate Pond SC
    deactivate Distributor App
```
TBD - description  
Before approving the loan, the pond performs the following check:
- General pond check:
  * Pond is not stopped
  * There are available funds in the pond i.e. pond available funds > requested amount
- Loan request check - compare loan request parameters with smart contract's parameters:
  * User DID with verifiable credentials -> not empty
  * Requested loan amount -> between Min and Max amount; if outside of the range, the pond approves the nearest amount but does not reject the request
  * Request loan duration -> between Min and Max duration; if outside of the range, the pond approves the nearest amount but does not reject the request
- Eligibility check:
  * By providing the verification result to the Verification Registry smart contract  
Once the loan is approved, the smart contract registers it on the chain and returns a response with the following parameters:
- Approved amount
- Approved duration (in months)
- Interest rate (APR) %
- Disbursement fee %
- Cash-back rate %
- Interest amount ( = Amount x APR x Duration/12)
- Total amount to be repaid ( = Amount + Interest amount)
- Installment amount ( = Total amount / Duration)
## Non-Custodial Model
TBD-description
