# Loan Disbursement
Disbursement of the loans occur immediately after a loan is approved and registered on-chain. There are two approaches for disbursement implementation - off-chain and on-chain. Both models are presented below.
## On-Chain Model
In this scenario, the disbursement transactions are executed on-chain by the Pond smart contract.
```mermaid
sequenceDiagram
    participant SSFI App
    participant Borrower EOA
    participant Pond SC
    participant Loan Registry SC
    Note over SSFI App: Custodial via Distributor App or self-managed identity
    Note over Pond SC: ...Loan is approved
    activate Pond SC
    Pond SC->>Pond SC: Prepare "repayment commitment" message
    Pond SC->>+SSFI App: Request signature of "repayment commitment" message
    SSFI App->>-Pond SC: Sign message
    Pond SC->>Borrower EOA: Transfer loan amount
    alt Transfer is successful?
        Pond SC->>Loan Registry SC: Register "repayment commitment" message
    else Transfer not successful?
        Pond SC->>Pond SC: Destroy "repayment commitment" message
    end
    deactivate Pond SC
```
Loan disbursement is executed as a final step of the Loan Application process immediately after [Loan Approval](./C-Risk-Mgmt-3-Loan-Approval.md).
  
Before releasing the amount to the Borrower's account, the Pond smart contract creates a lightweight privacy-preserving message called **"repayment commitment"**. The message contains information about the Borrower's SSFI address, Loan Id and next installment date and amount. It represents a promise that the Borrower will make this payment. The messages is hashed and signed using Borrower's SSFI and then registered in the Loan Registry smart contract.
## Off-chain Custodian Model
In this scenario, the disbursement transactions are executed off-chain but the protocol receives "proof-of-pay" notifications about them.
```mermaid
sequenceDiagram
    participant Distributor App
    participant Payment Processor
    participant Pond SC
    participant Loan Registry SC
    Note over Distributor App: ...Loan is approved
    activate Distributor App
    Distributor App->>+Payment Processor: Order payment
    Payment Processor->>Payment Processor: Execute payment
    Payment Processor->>-Distributor App: Return payment proof
    Distributor App->>Pond SC: Send payment proof
    deactivate Distributor App
    activate Pond SC
    Pond SC->>Pond SC: Prepare "repayment commitment" message
    Pond SC->>+Distributor App: Request signature of "repayment commitment" message
    Distributor App->>-Pond SC: Sign message
    Pond SC->>Loan Registry SC: Register "repayment commitment" message
    deactivate Pond SC
```
Loan disbursement is initiated after the loan is approved and it occurs off-chain. The Pond smart contract receives a **"proof-of-pay"** receipt from the Distributor App and based on it the smart contrat prepares the repayment commitment message, requests signature on it and registers it.

