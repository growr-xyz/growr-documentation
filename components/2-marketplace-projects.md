# Projects

## Description

*Projects* are a key component of the decentralized marketplace. Each project represents a loan offer with predefined conditions and eligibility criteria. Every loan in the protocol is approved and disbursed from a project. Projects with similar risk parameters and goals are combined into lending pools.

## Characteristics

The project has the following main characteristics:
 - *Initiated by:* Lender / Borrower / Distributor (on behalf of borrowers)
 - *Owned by:* The initiator
 - *Funded by:* Lender (direct first-loss capital) + Investors (through a lending pool)
 - *Funding to:* Borrowers having the required set of verifiable credentials
 - *Time period:* Fixed upon creation
 - *Available amount:* Variable, depending on the funding operations
 - *Limit amount:* Defined upon creation, could only be increased
 - *Interest rate:* Fixed upon creation
 - *Project-based collateral:* Yes, optional (as a reserved amount)
 
## Implementation

The protocol implements a *Project Factory smart contract* that enables the creation of new projects with varying credit line parameters and eligibility criteria. This smart contract is controlled by the Growr governance board (initially - Growr core developers) through a multi-sig account.
Project Factory contract functions:
 - Create a project
 - Destroy a project

Each project is created through the project factory as a separate *Project smart contract*. It enables users to apply for micro-loans from its funds. This smart contract is controlled by a lender.
Project contract functions:
 - Deposit funds
 - Withdraw funds
 - Extend limit
 - Activate lending
 - Deactivate lending
 - Close

## Project types

Projects may vary depending on the following specifics:
1. Initiation
Each project can be initiated by (1) a lender, (2) a borrower or (3) a distributor on behalf of borrowers. The initiator becomes a project owner.
2. Funding
Each project can be funded in one of the two possible payment approaches - (1) on-chain or (2) off-chain. 
In the *on-chain* payment approach, all transactions for depositing and withdrawing project funds are executed on-chain and processed by the protocol. In this scenario, the project might apply for additional liquidity from an automated lending pool. In the *off-chain* payment approach, project funds are only declared by the lender. 
3. Reserves / Collateral
Optionally, each project can have safety reserves - collateral used as a safety fund against defaulted loans. Those reserves are collected in 2 ways: (1) First-loss capital provided by the project owner upon creating the project or when extending its amount, or (2) Shared payments from the borrowers of the project (see next point). The reserved amount is released when the project is closed and after covering potential losses from defaulted loans.
4. Debt sharing
In terms of loan repayment, the projects can operate in two models. 
In the first model (*individual*), each borrower repays only his/her loan(s) from the project and unpaid loans remain in default. In the second model (*community*), unpaid loans are compensated by overpaid amounts of the repaid loans.
