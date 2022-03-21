# Borrower Credentials
The Growr protocol relies on a new type of decentralized identity that we call the **Self-sovereign Financial Identity (SSFI)**. It stores a user's unique global identity and contains various **Veriﬁable Credentials (VCs)** - provable claims associated with the DID of the user. For the SSFI implementaion, the protocol relies on W3C’s standards for Verifiable Credentials (VC).  
The verifiable credentials are issued from different sources and are used to assert creditworthness in front of the lending ponds.  
## Credentials Issuing
Credentials are provided by **Credential Issuers** – that is, centralized or decentralized third parties, asserting certain facts about the user.  
Below is a standard process for credential issuing for Borrowers using a custodial Distributor App. In non-custodial model, the process is the almost the same - instead of Distributor App, the user would use an agent app with connected self-managed wallet. The process follows the same pattern when credentials are issued to other protocol participants (eg. Lenders and Liquidity providers).
```mermaid
sequenceDiagram
    participant Borrower
    participant Distributor App
    participant Credential Issuer
    Borrower->>Distributor App: Provide data
    activate Distributor App
    Distributor App->>Credential Issuer: Request credential requirements & fee
    activate Credential Issuer
    Credential Issuer-->>Distributor App: Provide credential offer
    Distributor App->>Credential Issuer: Claim credential
    Credential Issuer->>Distributor App: Request proof
    Distributor App->>Credential Issuer: Provide signed proof
    Credential Issuer->>Credential Issuer: Issue credential
    Credential Issuer->>Distributor App: Return credential
    deactivate Credential Issuer
    Distributor App->>Distributor App: Store credential
    Distributor App-->>Borrower: "Issued credential"
    deactivate Distributor App
```
This issuing process could be part of the Onboarding process ([Borrower Onboarding section](./B-Borrower-Onboarding.md)) or could be executed on-demand.  
Several examples of verifiable credentials are presented in the sections below.
### KYC Credentials
In regulated custodial model, a verifiable credential for successfully passed KYC process (including AML/CFT risk check) is a must. Individual KYC credential can be requested from the Borrowers, when applying for a loan. In addition, institutional KYC credential could be requsted from investors, when trying to create a pond or pool, or when trying to deposit funds in it.  
KYC Credential Issuer could be any traditional identity verification service or the Distributor itself.
### Credit Score Credential
Issuing of credit score credentials can simplify the loan application process, especially in a custodial model. Instead of defining a complex eligibility criteria for the pond that will require Borrowers to collect multiple credentials in their SSFI, the Lender might request only one "combined" credential representing the overall credit score of the Borrower.
Credit Score Credential Issuer could be any risk scoring services, owned or accredited by a trusted Verifier.
### Financial Health Credential
The Growr protocol incentivizes good ﬁnancial health – that is, improving ﬁnancial literacy and behaviors. Thus, the protocol encourages including the Financial Health credentials to every pond eligibility criteria; that is, before applying for a loan, the user must go through education and mentoring for "financial health treatment".  
Financial Health Credential Issuer could be any educational service, voted as "trusted" by the protocol.
### Savings History Credential
The Growr protocol incentivizes good ﬁnancial discipline and habits. With this regard, the protocol encourages including "savings history" credentials to every pond eligibility criteria; that is, before applying for a loan, the user must create a habit for regular micro-payments to his saving account.    
Savings History Credential Issuer could be any financial institution (where the user has a saving account) or financial data processing service (to which the user provides account statement information), voted as "trusted" by the protocol.
### Social Vouching Credentials
Through social vouching, the Borrowers have the opportunity to create their personal networks. They can request and receive endorsement (in the form of Social Vouching credentials) from other users, and thus improve their creditworthness. We believe that endorsement and social affiliation will prove to be key instruments for reducing the cost of risk in decentralized lending environment.  
Social Vouching Credential Issuer could be any risk rewiver, accredited by a trusted Verifier, or any protocol user with certain reputation level (rules to be decided and voted by the protocol community).
### Loan History Credentials
Growr protocol aims at incentivizing positive borrowin behavior. With this regards, regular on-time loan payments of past loans should help the Borrower build a positive on-chain credit score, which can be further translated to better loan conditions. This is achieved through the issuing of "loan history" credentials.  
Loan History Credential Issuer is the Growr protocol itself. For more details, see [Loan disbursement section](./D-Loan-Payment-1-Disbursement.md) and [Loan repayment section](./D-Loan-Payment-2-Repayment.md).
## Credentials Verification
Verifiable credentials are consumed by **Verifiers** using the concepts and data models for **presentation exchange**.   
Below is a standard process for credential verification using a custodial Distributor App for the verification request. In non-custodial model, the process is the almost the same - instead of Distributor App, the user would use an agent app with connected self-managed wallet. The process follows the same pattern when credentials of other protocol participants (eg. Lenders and Liquidity providers) must be verified.  
```mermaid
sequenceDiagram
    participant Borrower (Subject)
    participant Distributor App
    participant Credential Verifier
    participant Trusted Registries
    Borrower (Subject)->>Distributor App: Request credentials verification
    activate Distributor App
    Distributor App->>Borrower (Subject): Select credentials
    Distributor App->>Distributor App: Build and sign credential presentation
    Distributor App->>Credential Verifier: Send credential presentation
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
        Credential Verifier->>Distributor App: Credential verified
        Note left of Credential Verifier: (Optionally) Send verification result
        Distributor App-->>Borrower (Subject): "Verified credential"
    else If not OK
        Credential Verifier->>Distributor App: Verification failed
        Distributor App-->>Borrower (Subject): "Invalid credential"
    end
    deactivate Credential Verifier
    deactivate Distributor App
```
The credential verification performed by the Verifier includes the following tasks:  
- Verify that the credential presentation is signed with the Subject's DID
- Verify that the credential is signed by a trusted Issuer
- Verify that the credential is not expired
- Verify that the credential is not revoked
This verification process is part of the overall loan approval process. For more details, see [Loan Approval section](./C-Risk-Mgmt-3-Loan-Approval.md).
## Credentials Revocation
Issuers might need to revoke a certain credential before is expires - when the subject is not longer eligible for the credential or when they need to correct or update the information in the credential. In order to achieve this, they must implement the W3C's standard for Status List - during credential issuing they would embed in the credential a url to fetch the revocation list and the index in the list that corresponds to the given credential.
