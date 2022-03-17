sequenceDiagram
    participant Borrower
    participant Distributor App
    participant Credential Verifier
    participant Pond SC
    participant Verification Registry SC
    Note over Borrower: ...Borrower has credentials and loan offer
    Borrower->>Distributor App: Accept loan offer
    activate Distributor App
    Distributor App->>Distributor App: Create credential presentation
    Distributor App->>Credential Verifier: Present credentials
    activate Credential Verifier
    Credential Verifier->>Credential Verifier: Verify credentials
    alt credentials not OK?
        Credential Verifier-->>Distributor App: Failed verification
        Distributor App-->>Borrower: "Verification failed"
    else credentials OK?
        Credential Verifier->>Credential Verifier: Issue & sign verification result
        Credential Verifier-->>Distributor App: Return verification result
        Note right of Credential Verifier: Record is not stored!
    end
    deactivate Credential Verifier
    Distributor App->>Pond SC: Apply for loan (with verification result)
    activate Pond SC
    Pond SC->>Verification Registry SC: Send verification result + pond criteria
    activate Verification Registry SC
    Verification Registry SC->>Verification Registry SC: Validate verifier
    Verification Registry SC->>Verification Registry SC: Validate criteria matching
    Note right of Verification Registry SC: Eligibility check by Registry!
    Verification Registry SC-->>Pond SC: Validation result
    deactivate Verification Registry SC
    alt result not OK?
        Pond SC-->>Distributor App: Loan rejected
        Distributor App-->>Borrower: "Loan rejected"
    else result OK?
        Pond SC->>Pond SC: Approve & register loan
        opt
            Note over Pond SC: Loan disbursement...
        end
        Pond SC-->>Distributor App: Loan approved
        Distributor App-->>Borrower: "Loan approved"
    end
    deactivate Pond SC
    deactivate Distributor App  