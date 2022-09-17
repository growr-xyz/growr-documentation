<a name="ref-m2"></a># Borrower Credit Record

## Credit Record and Verifiable Credentials

The Growr protocol relies on a new type of decentralized identity that we call the **Self-sovereign Credit Record (SSCR)**. The _SSCR_ is intended to represent a borrower's unique global identity and financial record, storing various general-purpose and protocol-specific verifiable credentials. 

The _SSCR_ contains both hard information (facts such as credit score and history, debt-to-income ratio, bank account verification, and business financial indicators) and soft information (such as endorsement, community membership, and self-declared business plans) that are used in the credit risk assessment.

The verifiable credentials, stored in _SSCR_, are issued by trusted third parties called _credential issuers_. The credentials are issued and owned by the _borrower_, who is the subject of the credential. The _borrower_ presents a given set of his credentials when applying for a loan from the marketplace.

Below is a high-level diagram that depicts the lifecycle of the verifiable credentials:

```mermaid
sequenceDiagram
    participant Borrowing App
    participant CIS as Credential Issuing Service
    participant SSCR
    participant CVS as Credential Verification Service
    Note over CIS: Issuing verifiable credentials
    Borrowing App->>CIS: Claim credential
    CIS->>CIS: Issue credential
    CIS->>Borrowing App: Provide credential
    Borrowing App->>SSCR: Store credential
    Note over CVS: Verifying credentials
    SSCR->>Borrowing App: Provide credential
    Borrowing App->>CVS: Present credential
    CVS->>CVS: Verify credential
    CVS->>Borrowing App: Provide result
```

## Credential Issuing

Below is a standard process for issuing verifiable credentials:

```mermaid
sequenceDiagram
    participant Borrower
    participant Borrowing App
    participant CIS as Credential Issuing Service
    participant SSCR
    Note over Borrowing App: Custodial distribution app or Self-custody wallet
    Borrower->>Borrowing App: Provide data
    activate Borrowing App
    Borrowing App->>CIS: Request credential requirements & fee
    activate CIS
    CIS-->>Borrowing App: Provide credential offer
    Borrowing App->>CIS: Claim credential
    CIS->>Borrowing App: Request proof
    Borrowing App->>CIS: Provide signed proof
    CIS->>CIS: Issue credential
    CIS->>Borrowing App: Return credential
    deactivate CIS
    Borrowing App->>SSCR: Store credential
    Borrowing App-->>Borrower: "Issued credential"
    deactivate Borrowing App
```

## Credential Revocation

_Credential issuers_ might need to revoke a certain credential before it expires, eg. when the subject is no longer eligible for the credential or when they need to correct or update the information in the credential. To achieve this, they must implement the W3C's architecture design for Status List. According to this pattern, during credential issuing, the issuers would embed in the credential a URL to fetch a revocation list and the index in this list that corresponds to the given credential.

## Credential Verification

Below is a standard process for verifying credentials:

```mermaid
sequenceDiagram
    participant Borrower
    participant Borrowing App
    participant CVS as Credential Verification Service
    participant SSCR
    participant TSR as Trusted Service Registry
    participant CSL as Credential Status List
    Note over Borrowing App: Custodial distribution app or Self-custody wallet
    Borrower->>Borrowing App: Request credentials verification
    activate Borrowing App
    Borrowing App->>SSCR: Get credentials
    Borrowing App->>Borrowing App: Build and sign credential presentation
    Borrowing App->>CVS: Send credential presentation
    deactivate Borrowing App
    activate CVS
    CVS->>CVS: Verify borrower's signature
    CVS->>CVS: Verify issuer's signature
    CVS->>TSR: Check issuer
    CVS->>CVS: Verify credential validity
    opt  
        CVS->>CSL: Check credential status
    end
    alt If OK?
        CVS->>Borrowing App: Verification result
        activate Borrowing App
        Borrowing App-->>Borrower: "Verified credential"
        deactivate Borrowing App
    else If not OK
        CVS->>Borrowing App: Verification failed
        activate Borrowing App
        Borrowing App-->>Borrower: "Invalid credential"
        deactivate Borrowing App
    end
    deactivate CVS
```

<div style="page-break-after: always;"></div>
