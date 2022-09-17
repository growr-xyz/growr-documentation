<a name="ref-c3"></a># Loans

## Description

*Loans* represent the approved debts of each borrower. Each loan is released from a given project.

## Characteristics

The loan has the following main characteristics:
 - *Requested by:* Borrower
 - *Provided by:* Lender (through a project)
 - *Approved by:* Credential verification service, matching project requirements with borrower's presented credentials
 - *Time period:* Depends on the borrower's loan request and on project time limits
 - *Amount:* Fixed upon loan creation based on the borrower's loan request and presented credentials
 - *Interest rate:* Inherited by the project
 - *Loan collateral:* Not required

## Implementation

Loans are implemented as records in a loan book in each project smart contract.

## Loan types

Loans may vary depending on the following specifics:
1. Payments model
Each loan can be disbursed and then repaid in one of the two possible payment approaches - (1) on-chain or (2) off-chain. 
In the *on-chain* payment approach, all transactions for loan disbursement and repayment are executed on-chain and processed by the protocol. In the *off-chain* payment approach, the payment operations are settled by traditional payment providers, who issue and provide the protocol with "proofs-of-pay" to attest the payments are settled. 
2. Repayment schedule
Growr protocol supports 2 models for loan repayment. The first model is a *fixed repayment plan with monthly installments* and a predefined interest amount. The second model is with flexible *ad-hoc repayments*, and the interest amount is a variable calculated based on the period between disbursement and repayment(s). With the next protocol versions, we envision supporting other types of loans.

<div style="page-break-after: always;"></div>
