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
    Credential Verifier->>Pond SC: Get pond eligibility criteria
    Credential Verifier->>Credential Verifier: Validate criteria match
    Note right of Credential Verifier: Eligibility check by Verifier!
    Credential Verifier->>Credential Verifier: Verify credentials
    alt credentials not OK?
        Credential Verifier-->>Distributor App: Failed verification
        Distributor App-->>Borrower: "Verification failed"
    else credentials OK?
        Credential Verifier->>Credential Verifier: Issue & sign verification result
        Credential Verifier->>Verification Registry SC: Provide verification result & signature
        activate Verification Registry SC
        Verification Registry SC->>Verification Registry SC: Confirm & sign the result
        Verification Registry SC->>Verification Registry SC: Store verification record
        Note right of Verification Registry SC: Record is stored!
        Verification Registry SC-->>Credential Verifier: Result validated
        deactivate Verification Registry SC
        Credential Verifier-->>Distributor App: Confirmed verification
    end
    deactivate Credential Verifier
    Distributor App->>Pond SC: Apply for loan
    activate Pond SC
        Pond SC->>Verification Registry SC: Check verification record
        alt record not found or expired?
            Pond SC-->>Distributor App: Loan rejected
            Distributor App-->>Borrower: "Loan rejected"
        else record OK?
            Pond SC->>Pond SC: Approve & register loan
            opt
                Note over Pond SC: Loan disbursement flow...
            end
            Pond SC-->>Distributor App: Loan approved
            Distributor App-->>Borrower: "Loan approved"
        end
    deactivate Pond SC
    deactivate Distributor App  