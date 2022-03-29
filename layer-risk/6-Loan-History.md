# Loan History
## Loan Registry
Loan Registry smart contract is responsible to keep track of the loan history. The registry represents a chain of encrypted "repayment commitments" registered by the different Pond smart contracts. For more information on the events registration, see [Loan Disbursement](./3-Loan-Disbursement.md) and [Loan Repayment](./4-Loan-Repayment.md).

How it works? Each "repayment commitment" record contains information about the Borrower's SSFI address, Loan Id and next installment date and amount. When a Borrower repays an installment, the record is marked as expired/invalid and a new record is registered. When a Borrower fully repays a loan, the last record is invalidated but no new commitment record is registered. Valid (active) repayment commitment records with due date in the past will be indicators of overdue loans. Since all Pond smart contracts use the same Loan Registry, the latter can be used to determine the entire credit history of a given Borrower.
  
The data stored in the Registry smart contract does not contain any personal data and is encrypted in a way that only the owner of the SSFI key (the Borrower) can decrypt his/her credit history.

## Loan History Credentials
As a register of loan related events, the Loan Registry smart contract is able to provide on-chain proof of the loan history of a given Borrower. The proof can be converted to a verifiable credential by a Credential Issuer and used by the Borrower in subsequent loan application.
```mermaid
sequenceDiagram
    participant Borrower
    participant Borrowing App
    participant Credential Issuer
    participant Loan Registry SC
    Note over Borrowing App: Custodial distribution app or Self-custody wallet
    Borrower->>Borrowing App: Request credential
    activate Borrowing App
    Borrowing App->>Borrowing App: Prepares a key (signed hash)
    Note right of Borrowing App: This is SSFI's key to the registry
    Borrowing App->>Credential Issuer: Send a key and request credential
    activate Credential Issuer
    Credential Issuer->>Loan Registry SC: Extract history using the provided key
    Credential Issuer->>Credential Issuer: Issue credential
    Credential Issuer->>Borrowing App: Return credential
    deactivate Credential Issuer
    Borrowing App->>Borrowing App: Store credential
    Borrowing App-->>Borrower: "Issued credential"
    deactivate Borrowing App
```