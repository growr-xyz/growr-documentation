# Protocol mechanics

## How it works

The following diagram provides a high-level overview of the Growr protocol.

![How it works](../images/growr-how-it-works.svg)

Below is a summary of the protocol mechanics depicted on the diagram:

1. The _borrower_ is onboarded on a platform, provided by an _originator_ (such as a cooperative, guild, wholesale buyer, digital wallet, or another provider), where the borrower defines their funding needs.
2. One or more _trusted parties_ provide credentials to the _borrower_ to start building their self-sovereign credit record.
3. The _originator_ creates a loan offer in the form of a project with details about the local activities and the financing needs of the borrowers, to receive a credit line from the _decentralized marketplace_.
4. A _capital provider_ reviews the projects with their predefined eligibility criteria, assesses the risk and approves the credit line if it fulfills the risk policy. The _capital provider_ deploys additional funding to the project as a senior tranche via the _decentralized marketplace_, fully delegating the actual lending activity to the _originator_ and the protocol.
5. _Borrowers_ go through a simple application process to receive a loan from the _decentralized marketplace_ after asserting their eligibility with their verifiable credentials. 
6. The disbursed amount is received by the _borrowers_ in the borrowing application or directly paid to a _trusted party_, such as a merchant or a supplier, who provides the necessary goods and services to the borrower to achieve their goals.

The Growr protocol aims at standardization of the protocol mechanics. However, depending on the protocol participants and the tools and services they use, implementation details might vary. In general, we can distinguish the following use case specifics.

* _Origination_: access to the protocol is provided in a custodial model by an independent originator, or in a non-custodial model directly using a decentralized borrowing application.
* _Risk assessment_: performed by the originator with an internal risk assessment function, or by an independent trusted risk assessor.
* _Loan payments_: they are processed on-chain as part of the protocol mechanics or off-chain.

## Protocol participants

### Borrowers

_Borrowers_, represented by self-employed, micro-businesses, and smallholder farmers, apply for productive loans from the marketplace, most often with the help of a local originator, and then repay the loan plus its price.

### Originators

_Originators_ facilitate access to the protocol by grouping several borrowers with similar needs and presenting project applications to the marketplace on their behalf. They publish offers to the loan marketplace by creating _projects_ on behalf of the borrowers. The originators provide junior (first-loss) capital to finance the whole project or part of it. They can be:

* _Local cooperatives, guilds or other community organizations_ that are formed by borrowers to gain better access to loans and to standardize their relationship with the rest of the participants in the ecosystem.
* _Federated Chaumian mints_ [[21]](#ref21), enabling access to micro-financing to their users.
* _Telcos, retailers and gig-economy platforms_ that onboard and vet the users into their services and then facilitate their access to the protocol as an embedded financial service.
* _Digital wallets and fintech providers_ that already offer financial services and that can expand to unsecured decentralized lending.

### Trusted parties

_Trusted parties_ assert facts about the borrowers in the form of verifiable credentials. They can be:

* The _originator_, issuing credentials for its members or users.
* _Merchants, buyers, unions, chambers or other local organizations_ that serve the community or have knowledge of their members.
* _Independent third-party data providers_ that can issue credentials related to the activity of the borrower and relevant to the risk assessment process, such as KYC/AML, account data, and on-chain activity.
* _Financial health providers_ that publish educational materials and tools to help borrowers develop good financial habits and issue credentials that assert knowledge, skills, and accomplishments.

### Capital providers 

_Capital providers_ can be decentralized finance protocols or large institutional or individual investors who allocate senior capital to the loan marketplace and delegate the actual lending activity to the originators in the form of senior tranches for the financed projects.

### Decentralized marketplace

The _global decentralized micro-lending marketplace_ is provided by Growr through a set of open-source services. They enable originators to publish loan offers with predefined conditions and eligibility criteria, and borrowers to apply and get financing using credentials from their self-sovereign credit record.

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
   <td>Access to productive capital at a fair price. Optional “cash-back”-like rewards paid by the originator for positive behavior (e.g., on-time repayment).
   </td>
   <td>Build their self-sovereign credit record with the ability to use it for future financing needs.
   </td>
  </tr>
  <tr>
   <td><strong>Trusted party</strong>
   </td>
   <td>One-time fee paid by the borrower upon VC issuing (optional). Financial health rewards paid by the originator after on-time loan repayment (optional).
   </td>
   <td>Success and growth of the community.
   </td>
  </tr>
  <tr>
   <td><strong>Originator</strong>
   </td>
   <td>Origination fee upon each loan disbursement. Interest margin (yield) from the borrowers.
   </td>
   <td>Success and growth of the community. Revenue growth for service providers. Access to more customers in the marketplace.
   </td>
  </tr>
  <tr>
   <td><strong>Capital provider</strong>
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

## How does Bitcoin enable this in a fundamentally better way?

First, Bitcoin provides a sound monetary foundation. It is the perfect store of value for long-term capital accumulation, which cannot be inflated or seized by governments or adversaries. It’s fully open and censorship-resistant in nature, which allows anyone to participate directly without the need to rely on intermediaries, creating a platform for building financial services outside of the traditional system.

Second, the Lightning network enables low-cost instant and global transfer of value—in bitcoin or fiat-pegged digital assets. This way, capital from anywhere in the world can reach even the most distant community directly, avoiding unnecessary costs.

Third, solutions such as federated Chaumian mints enable the creation of local circular economies based on bitcoin, based on community custody of self-sovereign digital identities, bitcoin and other digital assets. Bitcoin mints connected to the Lightning network make it possible for informal financial groups to become digital micro-banks and empower their members with a full set of financial services.

Fourth, smart contracts on Bitcoin side-chains such as Rootstock [[13]](#ref13) and Liquid enable global digital capital infrastructure and automated pooling of funds by capital providers, matching their investment criteria to community projects.
With the Growr protocol, community members can also build their self-sovereign identities and credit records, enabling them to apply for financing from capital providers connected to the global digital capital infrastructure.

