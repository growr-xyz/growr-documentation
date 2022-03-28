# Pond Funding
The Growr protocol enables Liquidity Providers to fund lending pools and ponds according to their risk/reward appetite. The protocol allows both funding models - custodial and non-custodial.

## Off-chain Custodian Model
The model with a Custodian has lower technology learning curve and protect the user funds from malicious actors. In this scenario, no matter whether the Lender uses own funds or applies to Liquidity Providers for funds, all transactions occur off-chain.

## On-chain Model
A pond can be funded in 2 ways – directly (independently) or by applying for funds from a global pool (with or without local self-participation). The sections below presents those 2 scenarios.

### Direct pond funding
Lenders, who has sufficient liquidity can also play the role of a Liquidity Provider and will fund its own pond, and also takes the entire generated yield.
```mermaid
sequenceDiagram
    participant Lender
    participant Lending App
    participant Pond SC
    participant Pond Factory SC
    Note over Pond SC: ...Pond is created
    Lender->>Lending App: Initiate pond funding
    activate Lending App
    Lending App->>Pond Factory SC: Get pond address
    Lending App->>+Pond SC: Deposit funds to pond address
    Pond SC->>Pond SC: Register deposit transaction
    Pond SC-->>-Lending App: Return deposit receipt
    Lending App-->>Lender: "Successful deposit"
    deactivate Lending App
    Pond SC->>Pond SC: Generate yield through lending
    Lender->>Lending App: Request widhrawal
    activate Lending App
    Lending App->>+Pond SC: Request withdrawal
    Pond SC->>Pond SC: Check available funds
    Pond SC->>Pond SC: Register withdrawal transaction
    Pond SC->>-Lending App: Send fund + yield
    Lending App-->>Lender: "Successful withdrawal"
    deactivate Lending App
```

### Pool-to-pond funding
Local ponds can apply for funds from the pool resulting in so called "contract-to-contract (C2C) lending". Depending on the pond ﬁnancing period, fund requirements, proposed risk model and eligibility criteria, the pool owner (Liquidity Provider) decides to approve or not the funding to the pond. This is how it works:
```mermaid
sequenceDiagram
    participant Lending App (Lender)
    participant Pond Factory SC
    participant Pond SC
    participant Pool SC
    participant Lending App (LP)
    Note over Pool SC: ...Pool is created and funded
    activate Lending App (Lender)
    Lending App (Lender)->>+Pond Factory SC: Request pond creation
    Note right of Lending App (Lender): Pass Pool address as parameter
    deactivate Lending App (Lender)
    Pond Factory SC->>Pond Factory SC: Validate parameters
    Pond Factory SC->>+Pond SC: Create pond
    activate Pond SC
    Pond Factory SC-->>-Lending App (Lender): "Pond address"
    activate Lending App (Lender)
    Pond SC->>Pool SC: Register credit limit application
    deactivate Pond SC
    Lending App (Lender)-->>+Lending App (LP): Request for credit limit
    deactivate Lending App (Lender)
    Lending App (LP)->>Lending App (LP): Approve credit limit
    Lending App (LP)->>-Pool SC: Whitelist the pond
    Note over Pond SC: Utilization above %
    activate Pond SC
    Pond SC->>+Pool SC: Request loan amount
    Pool SC->>Pool SC: Approve request
    Pool SC->>-Pond SC: Disburse amount
    deactivate Pond SC
    loop Regular interest repayment
        Pond SC->>Pool SC: Repay interest
    end
    Note over Pond SC: Utilization below %
    activate Pond SC
    Pond SC->>+Pool SC: Repay loan amount
    Pool SC-->>-Pond SC: Confirm repayment
    deactivate Pond SC
```
If a Lender considers using liquidity from a Pool, he configures the Pool's address during Pond creation so the newly created Pond smart contract automatically registers credit limit request on the Pool smart contract function.

The Pool owner (Liquidity Provider) can approve this request by whitelisting the Pond address in the Pool smart contract. At any time, the Pool owner can block or change this credit limit.

Based on the Pond utilization, the Pond smart contract can automatically apply to the Pool smart contract for a loan (up to the credit limit). The Pond is required to regularly repay the interest fee to the Pool. Depending on the configured utilization threshold, the Pond can repay partially or fully the loan to the Pool smart contract.

This process ensures automatic liquidity management between the Pool smart contract and the whitelisted Pond smart contracts.

### Pool funding
Liquidity Providers are expected to directly fund their lending pools.
```mermaid
sequenceDiagram
    participant Liquidity Provider
    participant Lending App
    participant Pool SC
    participant Pool Factory SC
    Note over Pool SC: ...Pool is created
    Liquidity Provider->>Lending App: Initiate Pool funding
    activate Lending App
    Lending App->>Pool Factory SC: Get Pool address
    Lending App->>+Pool SC: Deposit funds to Pool address
    Pool SC->>Pool SC: Register deposit transaction
    Pool SC-->>-Lending App: Return deposit receipt
    Lending App-->>Liquidity Provider: "Successful deposit"
    deactivate Lending App
    Pool SC->>Pool SC: Generate yield through funding ponds
    Liquidity Provider->>Lending App: Request widhrawal
    activate Lending App
    Lending App->>+Pool SC: Request withdrawal
    Pool SC->>Pool SC: Check available funds
    Pool SC->>Pool SC: Register withdrawal transaction
    Pool SC->>-Lending App: Send fund + yield
    Lending App-->>Liquidity Provider: "Successful withdrawal"
    deactivate Lending App
```