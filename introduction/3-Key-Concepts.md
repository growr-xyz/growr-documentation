# Key Concepts

## Decentralized identity

### Decentralized identifiers and verifiable credentials 

The protocol implements the W3C’s standards (recommendations) for _Decentralized Identifiers_ (DIDs) [[14]](#ref14) and the _Verifiable Credentials Data Model_ (VCs) [[15]](#ref15). 

The DID is a new type of identifier that enables verifiable, decentralized digital identity. DIDs are URIs that associate a DID subject (e.g., a person, organization, thing, data model, abstract entity, etc.) with a DID document allowing trustable interactions associated with that subject. DIDs have been designed so that they may be decoupled from centralized registries, identity providers, and certificate authorities. Specifically, while other parties might be used to help enable the discovery of information related to a DID, the design enables only the controller of a DID to prove control over it without requiring permission from any other party.

The VCs are global uniformed provable claims associated with the subject of the DID. They are cryptographically secure, privacy-respecting, tamper-evident and machine verifiable. They can be used to build universally verifiable presentations, which can also be cryptographically verified.

Verifiable credentials are provided by _credential issuers_—i.e., centralized or decentralized third parties—asserting certain facts about the DID owner. Verifiable credentials are consumed by _verifiers_ using the concepts and data models for _presentation exchange_. Verifiers ensure that the credential presentation is signed with the subject’s DID, it is signed by a trusted Issuer, it is not expired and it is not revoked.

### Self-sovereign credit record

The Growr protocol relies on a new type of decentralized identity built using DIDs and VCs that we call the _self-sovereign credit record (SSCR)_. The SSCR is intended to represent a borrower's unique global identity and financial record, storing various general-purpose and protocol-specific verifiable credentials based on the borrower’s on-chain activity, trusted off-chain data, peer vouching, financial health metrics, and others.

The SSCR contains both hard information (facts such as credit score and history, debt-to-income ratio, bank account verification, and business financial indicators) and soft information (such as endorsement, community membership, and self-declared business plans) that are used in the credit risk assessment.

Verifiable credentials in an SSCR can be (but are not limited to):

* _KYC credential_ (hard information). This credential proves, possibly in a zero-knowledge manner, a successfully passed KYC process (including AML/CFT risk check) and can be issued by any distributor or a traditional third-party identity verification service. While not necessarily contributing to the risk assessment, the presence of such credentials may be a prerequisite for certain regulated lenders to provide funding.
* _Financial data credential_ (hard information). This credential contains various financial data of a borrower, such as products and transaction history, and can be issued by any account servicing financial institution or a trusted financial data provider.
* _Business activity credential_ (hard information). Data about the business activity such as income statement, cash flow, and/or balance sheet.
* _Savings history credential_ (hard information). This credential proves that the user is making regular micro-payments to his/her saving account. It could be issued by any trusted financial institution or savings account provider.
* _Credit history credential_ (hard information). History of the borrower’s past loans from the protocol or any external trusted sources.
* _Credit score credential_ (hard information). This is a credential that summarizes other atomic credentials and represents the overall credit score of the borrower.
* _Community membership credential_ (soft information). This credential is issued by a local organization (cooperative, union, chamber) or an employer, asserting the membership of the borrower in the organization.
* _Social vouching credential_ (soft information). This credential is received by endorsement from other protocol users, who have a certain reputation level and/or are trusted by the protocol.
* _Financial health credential_ (soft information). This is a special credential issued by the protocol itself for successfully passing “financial health treatment” through education and/or mentoring, as well as earned through regular on-time repayments of past loans received through the protocol.

## Lending and borrowing

### A brief history of debt

The concept of lending and borrowing is probably as old as the Sumer civilization around 3500 BC [[5]](#ref5). However, this often brought social tension—a significant part of the farmers would become over-indebted and be forced to sell their kids into debt slavery. Due to this fact, jubilees (cancellations of all debts) were often initiated by the rulers.

After the advent of coinage, banking and lending money against interest emerged as a business activity. This however often led to usury, or lending money at unreasonably high rates of interest out of the formal institutions, which was naturally considered sinful by most religions and outlawed by many states throughout history. Still, this practice continues today around the world, especially in communities with high informality and without access to financial services [[16]](#ref16).

In the Middle Ages, the notion of _interesse_ (from which “interest” originally comes) began to be accepted as a non-usurious compensation for the profit a merchant would have made, had they placed it in some profitable investment.

### Modern banking and financial inclusion

In modern banking, a loan is given to a borrower against interest and fees, which highly depend on the local context. Today, most countries have regulations on maximum interest rates. In Islamic banking where interest (riba) is forbidden, productive financing is provided through risk-sharing instruments.

However, even with regulated interest rates, the price of banking services is high, especially for almost a billion people around the world who live under the international poverty line of around $2/day. This is mostly due to the cost of distribution, as banks traditionally rely on physical infrastructure, as well as due to information asymmetry, which limits the appetite of banks to lend to informal micro-enterprises and leads to credit rationing.

To assess borrower risk, banks use the services of credit bureaus—private companies or government agencies that collect data about borrowers from various sources. But people without prior credit history may find themselves trapped in a loophole as banks may not be willing to serve them at all. In the end, being poor becomes very expensive because the financially excluded easily fall prey to loan sharks with usurious conditions.


### Microfinance

Microfinance has emerged as an alternative to banking, as a large-scale, businesslike provision of financial services to the poor. Microfinance institutions (MFIs) usually lend money to large groups of people in dense regions, in a minimally subsidized way. To monitor and manage multiple borrowers, MFIs rely on a combination of reputation, knowledge of the client, collateral, cosigners, and enforceable contracts.

Although it has its roots in the Middle Ages, microfinance was reinvented in a scalable model in the late 1970s. Witnessing extreme poverty and a deadly famine in his country Bangladesh, Professor Muhammad Yunus came up with the noble vision to provide microcredit—and later more financial services—to poor communities, in a fair and sustainable manner, and help them out of poverty [[17]](#ref17).

However, over the last decades, there has been a significant deviation from this original purpose, with many MFIs changing their focus from social impact to profit and replicating the narrative but not the good practices. In some well-publicized cases, MFIs have contributed to increasing poverty rather than decreasing it.

### Decentralized lending protocols

Since 2020, an increasing number of decentralized borrowing and lending protocols have been emerging fast in the decentralized finance (DeFi) space. They aim to fundamentally reinvent the financial infrastructure, enabling people to transact with each other globally, securely and in a permissionless manner. 

While most of the activity in the space is outside of the Bitcoin ecosystem, projects such as Tropykus and Sovryn built on Bitcoin’s side-chain Rootstock (RSK) are promising to bring decentralized lending to Bitcoin. 

Decentralized finance protocols still target mostly advanced users and let them lend or borrow digital assets without going to a centralized intermediary. Users deposit digital assets into liquidity pools, which become funds that the protocol can lend out to other users. Decentralized finance protocols aim to automate lending and would not be willing to assess individual borrowers. That is why they require collateral. This means that the on-chain assets of the borrower are used to secure a loan. The borrower provides the asset to secure the loan, and if the borrower defaults on the loan, the lender can take possession of the asset and sell it to cover the loss. Moreover, they often require over-collateralization, i.e. the value of locked assets as collateral must significantly exceed the loan amount. Currently, decentralized finance usage is higher in developed markets and by institutional investors [[18]](#ref18).

### Open and transparent credit data  

The Growr protocol approaches lending differently. The protocol aims at providing instant unsecured loans based on risk assessment and verifiable credentials, instead of requiring on-chain collateral. It provides an open credit record model, which also preserves the privacy of the borrowers through a self-sovereign identity, instead of relying on risk data locked within proprietary databases. 

A large percentage of the global population remains with limited access to credit due to immigration, lack of credit history or due to negative reporting to credit bureaus in case of late bills—even when the invoice was never received by the debtor [[19]](#ref19). In contrast to the traditional credit bureaus, the protocol puts the users in control of their data by storing their credit record in “their own pocket” without dependence on any central authority or intermediary. This way, the protocol aims at enabling borrowers to build a credit record based on alternative and relevant data sources, such as trusted organizations, financial health metrics, and peer vouching.

Borrowers collect credentials into their self-sovereign credit record, lenders use these credentials to better assess creditworthiness, and trusted parties are incentivized by the protocol to provide the credentials.

## Financial health

Dealing with money, especially borrowed from others, requires knowledge and high responsibility. Unfortunately, only 33% of people are financially literate [[20]](#ref20) and more than half of the global population is living without any savings [[1]](#ref1).

That is why the Growr protocol aims to incentivize providers who help borrowers to improve their financial health through education and tools promoting good behavior. Borrowers’ financial health credentials can be used in the risk assessment to improve loan conditions and providers get rewarded based on the actual benefit provided to the borrowers.

<div style="page-break-after: always;"></div>
