# Protocol Processes

## Processes
Growr protocol's operation is defined by a framework consisting of the following processes:
- Distribution & Identity
  * Onboarding
  * Credentials issuing
  * Credentials verification
- Risk Management
  * Loan Offering
  * Loan Approval
  * Loan Disbursement
  * Loan Repayment
  * Loan Collection
  * Loan History
- Liquidity
  * Pond Creation
  * Pond Funding
  * Pond Profitability
- Payments
  * On-chain Payments
  * Off-chain Payments
- Governance
  * Protocol Governance

The Growr protocol aims at standardization of the above processes, and this is especially valid for the risk management processes. However, depending on the protocol participants and the tools and services they use, details about certain process implementation might vary. In general, we can summarize the implementation models in 2 categories - custodial and non-custodial.

## Custodial Model
In custodial model, the Borrowers access the protocol via Borrowing app, provided by regulated last-mile financial service providers. The self-sovereign financial profile is also under custody. Payments are managed by off-chain custodian (payment processor).

![Growr Custodial model](../images/growr-custodial.png)

## Non-Custodial Model
The non-custodial model allows full decentralization of the protocol. Borrowers access the protocol using a dApp having their wallet connected and all transactions are executed on-chain.

![Growr Non-Custodial model](../images/growr-non-custodial.png)