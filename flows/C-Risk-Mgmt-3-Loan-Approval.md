# Loan Approval
## Custodial Model
Smart contracts are usually not technically capable and economically practical at executing the verification operations themselves, and they cannot call upon external verification services beyond the constraints of their own chain. Therefore, the exchange and verification of credentials are executed off-chain and then confirmed on-chain.
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
    Note right of Risk Assessor: See: Credential verification
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
    Verification Registry SC->>Verification Registry SC: Validate Verifier
    Verification Registry SC-->>Pond SC: Validation result
    deactivate Verification Registry SC
    alt result not OK?
        Pond SC-->>Distributor App: Loan rejected
        Distributor App-->>Borrower: "Loan rejected"
    else result OK?
        Pond SC->>Pond SC: Approve loan & register on-chain
        opt
            Note over Pond SC: See: Loan disbursement
        end
        Pond SC-->>Distributor App: Loan approvedx
        Distributor App-->>Borrower: "Loan approved"
    end
    deactivate Pond SC
    deactivate Distributor App
```
The key role in the process goes to the Risk Assessor who safely and securely perform the following assessment:  
- Verify that the Borrower has all the necessary credentials
- Verify that the presented credentials have valid signatures
- Optionally request and ensure that the loan application is reviewed and confirmed
- Optionally request and ensure that the Borrower has the necessary credit score  
Upon succesful completion of all verification checks, the Risk Assessor creates a lightweight privacy-preserving **Verification Result** assesting that a given Borrower matches the eligibility criteria of a given pond. The Risk Assessor hashes and signs the result and return it back to the Distributor App for further use in the smart contract transaction. Note that the verification result does not contain credentials to prevent leakage of sensitive personal information on-chain.  
Having the result from the Risk Assessor, the Distributor calls the loan application function of the Pond smart contract. The latter passes the verification result and Risk Assessor's signature as parameters to the Verification Registry contract function for validation. The registry uses the signature and the verification result to confirm whether or not the result corresponds to the public address of a known verifier configured in the registry contract.   
After validating the Borrower and before approving the loan, the pond performs the following final checks:
- General pond check:
  * Pond is not stopped
  * There are available funds in the pond i.e. pond available funds > requested amount
- Loan request check - compare loan request parameters with smart contract's parameters:
  * User DID with verifiable credentials -> not empty
  * Requested loan amount -> between Min and Max amount; if outside of the range, the pond approves the nearest amount but does not reject the request
  * Request loan duration -> between Min and Max duration; if outside of the range, the pond approves the nearest amount but does not reject the request
- Eligibility check:
  * By receiving confirmation of the verification result from the Verification Registry smart contract  
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
The non-custodial loan approval flow is almost the same. The main difference is that instead of Distributor App, the borrower would use an agent app with connected self-managed wallet.
