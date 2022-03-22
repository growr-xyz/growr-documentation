# Loan Repayment
Loans in Growr protocol are designed to be repaid on-chain through regular installments. Borrowers are allowed to repay an amount different than the regular installment amount.  
There a two approaches for repayment implementation - off-chain and on-chain. Both models are presented below.
## On-Chain Model
In this scenario, the repayment transactions are executed on-chain by the Pond smart contract.
```mermaid
sequenceDiagram
    participant SSFI App
    participant Borrower EOA
    participant Pond SC
    participant Loan Registry SC
    Note over SSFI App: Custodial via Distributor App or self-managed identity
    Borrower EOA->>+Pond SC: Transfer repayment amount
    Pond SC->>Pond SC: Register repayment
    Pond SC->>Pond SC: Prepare new "repayment commitment" message
    Pond SC->>+SSFI App: Request signature of new "repayment commitment" message
    SSFI App->>-Pond SC: Sign message
    Pond SC->>Loan Registry SC: Expire old "repayment commitment" message
    Pond SC->>Loan Registry SC: Register new "repayment commitment" message
    alt In case of over-repayment or cash-back
        Pond SC->>Borrower EOA: Return amount
    end
    deactivate Pond SC
```
After receiving the repayment amount, the Pond smart contract process the repayment:  
- If repaid amount = installment amount -> normal installment repayment
- If repaid amount < installment amount -> partial installment repayment
- If repaid amount > installment amount -> normal + partial installment repayment
- If repaid amount = remaining loan amount -> final loan repayment
- If repaid amount > remaining loan amount -> final loan repayment + amount for return  
After registering the event, the Pond smart contract creates a new "repayment commitment" message for the next installment. The messages is hashed and signed using Borrower's SSFI and then registered in the Loan Registry smart contract. The old "repayment commitment" message is marked as expired/invalid.  
In case the Borrower qualifies for a cash-back payment (i.e. all installments are repaid on time), the Pond smart contract repays back the amount to the Borrower. Alternatively, to promote a better financial discipline, this cash-back amount can be time-locked and use a verifiable credential in further loan applications.
## Off-chain Custodian Model
In this scenario, the repayment transactions are executed off-chain but the protocol receives "proof-of-pay" notifications about them.
```mermaid
sequenceDiagram
    participant Distributor App
    participant Payment Processor
    participant Pond SC
    participant Loan Registry SC
    activate Distributor App
    Distributor App->>+Payment Processor: Request payment
    Payment Processor->>Payment Processor: Execute payment
    Payment Processor->>-Distributor App: Return payment proof
    Distributor App->>Pond SC: Send payment proof
    deactivate Distributor App
    activate Pond SC
    Pond SC->>Pond SC: Prepare new "repayment commitment" message
    Pond SC->>+Distributor App: Request signature of new "repayment commitment" message
    Distributor App->>-Pond SC: Sign message
    Pond SC->>Loan Registry SC: Expire old "repayment commitment" message
    Pond SC->>Loan Registry SC: Register new "repayment commitment" message
    deactivate Pond SC
```
Loan repayment is initiated and executed off-chain. The Pond smart contract receives a **"proof-of-pay"** receipt from the Distributor App and based on it the smart contrat prepares the repayment commitment message, requests signature on it and registers it.