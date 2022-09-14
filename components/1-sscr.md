# Self-sovereign Credit Record

## Description

The *Self-sovereign credit record (SSCR)* is a new type of decentralized identity built using W3C standards for decentralized identifiers (DIDs) and verifiable credentials (VCs). The SSCR is intended to represent a borrower's unique global identity and financial record, storing various general-purpose and protocol-specific verifiable credentials based on the borrower’s on-chain activity, trusted off-chain data, peer endorsement, financial health metrics, and others.

The SSCR contains both hard information (facts such as credit score and history, debt-to-income ratio, bank account verification, and business financial indicators) and soft information (such as endorsement, community membership, and self-declared business plans) that are used in the credit risk assessment.

## Characteristics
The verifiable credentials, stored in SSCR, have the following characteristics:
- *Issued by:* Trusted third parties (credential issuers)
- *Issued to:* Borrower
- *Owned by:* Borrower
- *Presented to:* Growr protocol (Project smart contract)
- *Verified by:* Credential verification service

## Implementation
The unique identity address is generated using an SSI framework such as Rif Identity. The verifiable credentials are stored in secure decentralized storage, such as Rif Data Vault.

## Credential types

### KYC credential

This credential proves a successfully passed KYC process (including AML/CFT risk check). It could be mandatory for certain regulated lenders to provide funding.
- Type: Hard information
- Used to prove: Identity
- Issued by: Distributor / Traditional third-party identity verification service

### Financial data credential

This credential contains various financial data of a user, such as products and transaction history. It shows the financial habits of the user, as well as the trends in his cash flow.
- Type: Hard information
- Used to prove: Creditworthiness
- Issued by: Distributor / Account servicing financial institution / Trusted financial data provider

### Business activity credential

This credential contains data about the business activity such as income statement, cash flow, and/or balance sheet. It can be used to prove past and future revenue.
- Type: Hard information
- Used to prove: Creditworthiness
- Issued by: Distributor / Trusted supplier or buyer / Trusted financial data provider

### Savings history credential
This credential proves that the user is making regular micro-payments to a savings account and thus shows the financial discipline of the user.
- Type: Hard information
- Used to prove: Creditworthiness
- Issued by: Distributor / Trusted financial institution / Savings account provider

### Credit history credential
This credential represents the borrower’s past loans from the protocol (or from external trusted sources).
- Type: Hard information
- Used to prove: Creditworthiness & Trustworthiness
- Issued by: Growr protocol

### Credit score credential
This is a credential that summarizes other atomic credentials and represents the overall creditworthiness of the borrower.
- Type: Hard information
- Used to prove: Creditworthiness
- Issued by: Risk assessor

### Financial health credential
This is a special credential issued for successfully passed “financial health treatment” through education and/or mentoring in embedded financial health incentivization tools.
- Type: Soft information
- Used to prove: Trustworthiness
- Issued by: Financial health provider / Growr protocol

### Community membership credential
This credential asserts the membership of the user in a given organization and the trust of the community.
- Type: Soft information
- Used to prove: Reputation
- Issued by: Local organization (cooperative, union, chamber, employer)

### Social endorsement credential
This credential is received by endorsement from other protocol participants, who have a certain reputation level and/or are trusted by the protocol.
- Type: Soft information
- Used to prove: Reputation
- Issued by: Any protocol participant
