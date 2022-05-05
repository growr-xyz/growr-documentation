# Key Concepts

## Decentralized identity

### DIDs
Growr protocol implements W3C’s standard for decentralized identity (DID). DID is a new type of identifier that enables verifiable, decentralized digital identity. DIDs are URIs that associate a DID subject (e.g., a person, organization, thing, data model, abstract entity, etc.) with a DID document allowing trustable interactions associated with that subject. DIDs have been designed so that they may be decoupled from centralized registries, identity providers, and certificate authorities. Specifically, while other parties might be used to help enable the discovery of information related to a DID, the design enables only the controller of a DID to prove control over it without requiring permission from any other party. 

### VCs
Growr protocol implements W3C’s standard for **Verifiable Credentials (VCs)**. Verifiable Credentials (VC) are global uniformed provable claims associated with the subject of the DID. They are cryptographically secure, privacy respecting, tamper-evident and machine verifiable. They can be used to build universally verifiable presentations, which can also be cryptographically-verified. 

Verifiable credentials are provided by **Credential Issuers** – that is, centralized or decentralized third parties, asserting certain facts about the DID owner. Verifiable credentials are consumed by **Verifiers** using the concepts and data models for **presentation exchange**. Verifiers verify that:
- The credential presentation is signed with the subject's DID.
- The credential is signed by a trusted Issuer.
- The credential is not expired.
- The credential is not revoked.

### Growr's Self-sovereign financial identity
The Growr protocol relies on a new type of decentralized identity that we call the **Self-sovereign Financial Identity (SSFI)**. The SSFI is intended to represent user's unique global identity and to store various protocol-specific verifiable credentials, coming from various sources such as on-chain activity, trusted off-chain data, peer vouching, and others.

Verifiable credentials can be (but are not limited to):
- *KYC* credential. This credential proves successfully passed KYC process (including AML/CFT risk check) and can be issued by any last-mile provider or a third-party traditional identity verification service.
- *Financial Data* credential. This credential contains various financial data of a user (such as products and transaction history) and can be issued by any financial institution.
- *Savings History* credential. This credential proves that the user is making regular micro-payments to his saving account. It could be issued by any trusted financial institution (where the user has a saving account) or trusted financial data processing service (to which the user provides account statement information).
- *Financial Health* credential. This is a special credential issued by trusted services for successfully passed "financial health treatment" through education and/or mentoring.
- *Credit Score* credential. This is a "combined" credential, summarizing other atomic credentials, and representing the overall credit score of the Borrower.
- *Social Vouching* credential. This credential is received by endorsement from other protocol users, who have certain reputation level and/or are trusted by the protocol.
- *Loan History* credential. This is a credential, issued by the protocol itself and is earned through regular on-time repayments of past loans received by the protocol.

## Decentralized lending

### Traditional lending & microfinance
In traditional lending, a loan is given by lenders (banks and other financial institutions) to borrowers, and the borrowers repay the loan together with the lending price (the interest). The lender determines all loan conditions - accepted risk levels, required collaterals, interest rates, fees, and etc. If the lender feels there's a higher risk of not being paid back by a borrower, they will charge that borrower a higher interest rate. With this model, being poor is actually very expensive. Very often, the poorest are either excluded from the financial system or they fall prey to financial sharks offering loans at expensive and unfair conditions.

Microfinance, as one of the lending model, aims at providing useful financial services to millions of people. Microfinance institutions (MFI) lend money on a large scale, usually to large group of people in dense regions, in a minimally subsidized, businesslike way. To monitor and manage multiple borrowing, MFIs rely on a combination of reputation, knowledge of the client, collateral, cosigners, and enforceable contracts. It is also very common for MFIs to use aggressive techniques to pursuit non-payers and press for repayment.

All current lending models have something in common - they use intermediate organizations because it is impossible for the large capitalist to come into direct contact with each individual. The capitalist has no local knowledge of the individual and he could not keep millions of small accounts. We need a radically different way to include the poor population to the formal financial system and to connect them with the wealthy people and organizations.

### Decentralized lending protocols
Decentralized Finance (DeFi) have the potential to fundamentally reinvent the financial infrastructure enabling people to transact with each other globally, securely and permissionless. Important share in the DeFi ecosystem is taken by decentralized lending protocols and liquidity markets.

Decentralized lending protocols let users lend or borrow digital assets without going to a centralized intermediary. Users deposit digital assets into liquidity pools, which become funds that the protocol can lend out to other users. A specific characteristic of the most popular protocols is that they require a collateral. This means that onchain assets of the borrower are used to secure a loan. The borrower provides the asset to secure the loan, and if the borrower defaults on the loan, the lender can take possession of the asset and sell it to cover their loss. Moreover, they often require overcollateralization i.e. the amount of locked assets as collateral exceeds the loan amount.

### Growr's decentralized credit risk management
Growr protocol approaches lending differently. The protocol aims at providing instant insecure loans based on risk assessment and verifiable credentials instead of requiring an on-chain collateral. How it works? Borrowers collect credentials into their own private financial record, Lenders use these credentials to better assess creditworthiness, and Trusted parties are incentivized to provide the credentials.

Growr protocol introduces an innovative approach for decentralized credit risk management, in which the responsibility is split between all protocol participants:
- *Credential Issuers* assert facts about the borrowers in the form of credentials.
- *Credential Verifiers* validates the credentials.
- *Risk Assessors* orchestrate the risk assessment activities and asserts borrower's eligibility to receive a loan.
- *Trusted Registries* validate that credentials are issued by trusted issuers and risk assessments are prepared by trusted risk assessors.
- *Smart Contracts* take decision based on the input from the above-mentioned risk management service providers.
- *Protocol Governance Board* decides which participants are trusted and excludes the ones that misbehave.

Each participant is incentivized by the protocol to fairly fulfil its duties, as follows:
- With positive behavior in terms of regularly repaid loans, *Borrowers* increase their credit risk score. And better risk score translates to better lending conditions - increased amount limit and decreased interest rate.
- Trusted parties (*Credential Issuers* and *Risk Assessors*) receive a fee for the services they provide. In case of poor execution of their risk management function, the respective participant is blacklisted from the protocol. In addition, risk management service providers might be required to stake protocol tokens as a guarantee for their fair participation.
- *Lenders* and *Liquidity Providers* distribute part of the profit with all participants to motivate them to properly execute their risk management functions in order to decrease their cost of default and respectively to increase their profit.

### Growr's 2-level pooling
The Growr protocol is able to operate on 2 levels – global pools and local ponds. Global pools are funded by Liquidity Providers who then delegate the actual lending activity to local guilds with local lending ponds.

A lending pool can be created by any institutional investor with enough capital who specifies the initial pool parameters. Liquidity Providers can safely deposit funds into lending pools according to their preferences and based on automatic vetting using their own SSFI and Verifiable credentials, e.g., applicable AML/CFT checks, required by the pool creator.

Lending ponds are created by local lenders. Different lenders have varying levels of risk tolerance, depending on the laws and regulations in their jurisdictions, as well as on their profit goals. Therefore, each pond can have its own parameters (such as loan amount and duration), rates and eligibility criteria.

Local ponds apply for funds from the pool resulting in so called "contract-to-contract (C2C) lending". Based on the Pond utilization, a Pond smart contract can automatically apply to a Pool smart contract for a loan (up to the approved credit limit). Depending on the pond financing period, fund requirements, proposed risk model and eligibility criteria, the pool owner decides to approve (i.e., to whitelist the Pond address in the Pool smart contract) or not the funding to the pond. The Pond is required to regularly repay the interest fee to the Pool. Depending on the configured utilization threshold, the Pond can repay partially or fully the loan to the Pool smart contract. 

Therefore, the protocol implements automatic pond liquidity management. Moreover, in some of the future protocol versions, we envision integration with lending pools of other liquidity protocols.

## Financial health

### Financial health dimensions
Dealing with money, especially borrowed from others, requires knowledge and high responsibility. That’s why it is very important that everyone gets a financial health treatment for long-term improvement of their financial health. It’s not about a single transaction, but achieving more throughout people's lives, and ultimately reaching a better lifestyle and financial independence.

Financial Health treatment includes building knowledge and proper habits in 4 financial dimensions:
- *Spending*. The Spending dimension is measuring how well people are balancing between the money they earn and the money they spend. Surprisingly, even people who earn a lot can spend their income without thinking too much. As a result, they live a paycheck-to-paycheck lifestyle, which prevents them to follow their dreams. Budgeting is a powerful tool!
- *Savings*. The Saving dimension shows how people are doing in terms of putting some money aside. Many people do not understand where to keep their money in order to protect it from inflation and other dangers that may prevent it to keep its value over time. Savings take people's financial life in their hands!
- *Borrowing*. The Borrow dimension demonstrates how well people are able to manage their debt. It assesses whether people are debt-free, whether they feel comfortable having a loan, and whether their debt is manageable or too much and leading to overdue payments.  Debt is not always bad – if people know how to use it!
- *Planning*. The Plan dimension is perhaps the most important indicator for people's ability to maintain financial health in the long run. Most people do not have a systematic approach to considering two key elements in financial planning -  potential risks and key life events in the future. Tomorrow starts today!

### Growr's incentivization concept
We, in Growr, understand that delivering money and financial services to the poor does not mean reducing their poverty. Therefore, the Growr protocol is designed to incentivize good financial health – that is, improving financial literacy and behaviors. 

To promote improving financial literacy and behaviors, Growr protocol encourages the implementation and use of the following concepts:
- **"Learn and earn"**; that is, before applying for a loan, the user must go through education and mentoring program in order to collect credentials for financial health improvement.
- **"Goal-based" financing**; that is, before applying for a loan, the user must declare a specific goal related to his/her real-life need, and deposit initial savings towards it.
- **"Savings discipline"**; that is, before applying for a loan, the user must create a saving habit by executing regular micro-payments to his saving account.

