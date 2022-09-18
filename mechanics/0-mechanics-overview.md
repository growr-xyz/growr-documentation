# Growr Mechanics Overview

## Protocol Processes

The following diagram provides a high-level overview of the Growr protocol mechanics.

![How it works](../images/growr-how-it-works.svg)

Below is a summary of the protocol processes depicted on the diagram:

1. The _borrower_ defines their funding needs to or in collaboration with a _distributor_, such as a cooperative, guild, wholesale buyer, digital wallet, or another provider. See the [Borrower Onboarding section](#ref-m1).
2. One or more _trusted parties_ provide credentials to the _borrower_ to start building their self-sovereign credit record. See the [Borrower Credit Record section](#ref-m2).
3. The _distributor_ applies for a project with details about the local activities and the financing needs of the borrowers, to receive a credit line from the _decentralized marketplace_.
4. A _risk assessor_, working for a _lender_, or a third party trusted by them, reviews each application, to assess the risk and determine the loan price and conditions.
5. A _lender_ (a bank, non-banking lender, or a fintech) approves the credit line if it fulfills the risk policy. Upon approval, the _lender_ creates a loan offer in the form of a project on the _decentralized marketplace_ with predefined eligibility criteria. See the [Project Setup section](#ref-m6).
6. _Investors_ can provide additional funding to the project as a senior tranche via the _decentralized marketplace_, fully delegating the actual lending activity to the lender and the protocol, according to their risk appetite. See the [Project Funding section](#ref-m7).
7. _Borrowers_ go through a simple application process to receive a loan from the _decentralized marketplace_ after asserting their eligibility with their verifiable credentials. See the [Loan Application section](#ref-m3). The disbursed amount is received by the _borrowers_ in the borrowing application, where they can make a direct payment to a merchant or use it in another way to achieve their goals. See the [Loan Disbursement section](#ref-m4).
8. _Borrowers_ can view and manage every aspect of their loans. They can easily pay off the loan, which helps them build their credit record and receive future loans with better conditions. See the [Loan Repayment section](#ref-m5).
9. Upon project closure, the collected amount is repaid with the following priority: 1) senior tranches (principal and yield) to _investors_, 2) junior tranches (principal and yield) to _lenders_, 3) rewards to _borrowers_. See the [Project Closure section](#ref-m8).

The Growr protocol aims at standardization of the protocol mechanics. However, depending on the protocol participants and the tools and services they use, implementation details might vary. In general, we can distinguish the following use case specifics.

* _Distribution_: access to the protocol is provided in a custodial model by an independent distributor, or in a non-custodial model directly using a decentralized borrowing application.
* _Risk assessment_: performed by a lender with an internal risk assessment function, or by an independent trusted risk assessor.
* _Funding_: provided partially by a lender with additional capital from global investors, or fully by the lender.
* _Loan payments_: they are processed on-chain as part of the protocol mechanics or off-chain.

## Protocol participants

### Borrowers

_Borrowers_, represented by self-employed, micro-businesses, and smallholder farmers, apply for productive loans from the marketplace, most often with the help of a local distributor, and then repay the loan plus its price.

### Distributors

_Distributors_ facilitate access to the protocol by grouping several borrowers with similar needs and presenting project applications to the marketplace on their behalf. They can be:

* _Local cooperatives, guilds or other community organizations_ that are formed by borrowers to gain better access to loans and to standardize their relationship with the rest of the participants in the ecosystem.
* _Federated mints_ [[21]](#ref21), enabling access to micro-lending to their users.
* _Telcos, retailers and gig-economy platforms_ that onboard and vet the users into their services and then facilitate their access to the protocol as embedded financial services.
* _Digital wallets and fintech providers_ that already offer financial services and can expand to unsecured decentralized lending.

### Trusted parties

_Trusted parties_ assert facts about the borrowers in the form of verifiable credentials. They can be:

* The _distributor_, issuing credentials for its members or users.
* _Merchants, buyers, unions, chambers or other local organizations_ that serve the community or have knowledge of their members.
* _Independent third-party data providers_ that can issue credentials related to the activity of the borrower and relevant to the risk assessment process, such as KYC/AML, account data, and on-chain activity.
* _Financial health providers_ that publish educational materials and tools to help borrowers develop good financial habits and issue credentials that assert knowledge, skills, and accomplishments.

### Lenders

_Lenders_ publish offers to the loan marketplace by creating and funding _projects_. The lenders provide first-loss capital to finance the whole project or part of it.

### Risk Assessors

_Risk assessors_ review project applications, assess the risk and determine the loan price and parameters. In most cases, this role is internally covered by the lender.

### Investors 

_Investors_ can be decentralized finance protocols or large institutional or individual liquidity providers who allocate capital to the loan marketplace through liquidity pools and delegate the actual lending activity to the lenders in the form of senior tranches for the financed projects.

### Decentralized marketplace

The _global decentralized micro-lending marketplace_ is the open-source smart contract infrastructure and the tools for decentralized lending.