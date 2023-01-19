# Protocol mechanics

## How it works

The following diagram provides a high-level overview of the Growr protocol.

![How it works](../images/growr-how-it-works.svg)

Below is a summary of the protocol mechanics depicted on the diagram:

1. The _borrower_ defines their funding needs to or in collaboration with a _distributor_, such as a cooperative, guild, wholesale buyer, digital wallet, or another provider.
2. One or more _trusted parties_ provide credentials to the _borrower_ to start building their self-sovereign credit record.
3. The _distributor_ applies for a project with details about the local activities and the financing needs of the borrowers, to receive a credit line from the _decentralized marketplace_.
4. A _risk assessor_, working for a _lender_, or a third party trusted by them, reviews each application, to assess the risk and determine the loan price and conditions.
5. A _lender_ approves the credit line if it fulfills the risk policy. Upon approval, the _lender_ creates a loan offer in the form of a project on the _decentralized marketplace_ with predefined eligibility criteria.
6. _Investors_ can provide additional funding to the project as a senior tranche via the _decentralized marketplace_, fully delegating the actual lending activity to the lender and the protocol, according to their risk appetite.
7. _Borrowers_ go through a simple application process to receive a loan from the _decentralized marketplace_ after asserting their eligibility with their verifiable credentials. The disbursed amount is received by the _borrowers_ in the borrowing application, where they can make a direct payment to a merchant or use it in another way to achieve their goals.

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
* _Telcos, retailers and gig-economy platforms_ that onboard and vet the users into their services and then facilitate their access to the protocol as an embedded financial service.
* _Digital wallets and fintech providers_ that already offer financial services and that can expand to unsecured decentralized lending.

### Trusted parties

_Trusted parties_ assert facts about the borrowers in the form of verifiable credentials. They can be:

* The _distributor_, issuing credentials for its members or users.
* _Merchants, buyers, unions, chambers or other local organizations_ that serve the community or have knowledge of their members.
* _Independent third-party data providers_ that can issue credentials related to the activity of the borrower and relevant to the risk assessment process, such as KYC/AML, account data, and on-chain activity.
* _Financial health providers_ that publish educational materials and tools to help borrowers develop good financial habits and issue credentials that assert knowledge, skills, and accomplishments.

### Lenders

_Lenders_ publish offers to the loan marketplace by creating and funding _projects_. The lenders provide junior (first-loss) capital to finance the whole project or part of it. They can be:

* _A bank, a non-banking lender, or a fintech company_ that deploys capital and taps into new market segments.
* The _distributor_ or a _trusted party_ (e.g. a supplier or a buyer) that helps the communities they serve with the necessary productive financing.

### Risk Assessors

_Risk assessors_ review project applications, assess the risk and determine the loan price and parameters. In most cases, this role is internally covered by the lender.

### Investors 

_Investors_ can be decentralized finance protocols or large institutional or individual liquidity providers who allocate senior capital to the loan marketplace and delegate the actual lending activity to the lenders in the form of senior tranches for the financed projects.

### Decentralized marketplace

The _global decentralized micro-lending marketplace_ is provided by Growr through a set of open-source services. They enable lenders to publish loan offers with predefined conditions and eligibility criteria, and borrowers to apply and get financing using credentials from their self-sovereign credit record.

## Participant incentives

<table>
  <tr>
   <td><strong>Role</strong>
   </td>
   <td><strong>Tangible incentives</strong>
   </td>
   <td><strong>Intangible incentives</strong>
   </td>
  </tr>
  <tr>
   <td><strong>Borrower</strong>
   </td>
   <td>Access to productive capital at a fair price. Optional “cash-back”-like rewards paid by the lender for positive behavior (e.g., on-time repayment).
   </td>
   <td>Build their self-sovereign credit record with the ability to use it for future financing needs.
   </td>
  </tr>
  <tr>
   <td><strong>Trusted party</strong>
   </td>
   <td>One-time fee paid by the borrower upon VC issuing (optional). Financial health rewards paid by the lender after on-time loan repayment (optional).
   </td>
   <td>Success and growth of the community.
   </td>
  </tr>
  <tr>
   <td><strong>Distributor</strong>
   </td>
   <td>Distribution fee upon each loan disbursement.
   </td>
   <td>Success and growth of the community. Revenue growth for service providers.
   </td>
  </tr>
  <tr>
   <td><strong>Lender</strong>
   </td>
   <td>Interest margin (yield) from the borrowers.
   </td>
   <td>Access to more customers on the marketplace. Reduced information asymmetry through the combination of self-sovereign credit record and on-chain history.
   </td>
  </tr>
  <tr>
   <td><strong>Risk assessor</strong>
   </td>
   <td>If there’s an independent risk assessor, a reward is paid by the lender after on-time loan repayment.
   </td>
   <td>
   </td>
  </tr>
  <tr>
   <td><strong>Investor</strong>
   </td>
   <td>Real-world yield on the invested capital.
   </td>
   <td>End-to-end transparency for the investments without intermediary counterparty risk.
   </td>
  </tr>
  <tr>
   <td><strong>Marketplace</strong>
   </td>
   <td>Protocol fee collected for the open-source project development.
   </td>
   <td>
   </td>
  </tr>
</table>

<div style="page-break-after: always;"></div>

## How does the Growr protocol contribute to Bitcoin?

The protocol contributes to the development of the Bitcoin ecosystem in several important dimensions:

* _Ethos:_ The protocol—built on top of Bitcoin—is used for solving real-life problems. We believe there is a gap in the available financial services for the poor—instead of building these on legacy or speculative rails, building them on Bitcoin strengthens Bitcoin's ethos.
* _Bringing more users._ Our vision is to bring the next 1B people on Bitcoin. By bringing more accessible financial services to the Bitcoin ecosystem—such as unsecured micro-loans—we bet on making Bitcoin even more attractive and accelerating its adoption. We are building a complementary solution to what already exists in the Bitcoin ecosystem.
* _Incentivizing adoption:_ The protocol enables the monetization of credentials issued by financial health providers (part of the trusted parties' role outlined above). Bitcoin missionaries promoting adoption can also act as such providers when they educate people about money and good financial habits. This works in the following way: a financial health provider issues verifiable credentials to a user (e.g., based on a test or proven skills), who stores these credentials as part of their self-sovereign credit record. When the borrower applies for a loan through the protocol, a risk assessor/lender uses these credentials for assessing the risk and providing access to micro-loans. And after the borrower repays the micro-loans in full without delays, a reward (a predefined part of the interest) goes to the financial health provider. This accelerates the adoption network effect through additional incentivization.
* _Additional revenue for miners:_ 80% of the fees of each transaction on the Rootstock (RSK) network goes as rewards to Bitcoin miners. The protocol will increase the usage and adoption of the Rootstock network, and this will increase the miners’ revenue. For more details, please see the “Why RSK is Important for the Bitcoin Ecosystem” section in the RSK whitepaper [[13]](#ref13).

