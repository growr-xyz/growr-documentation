# Key Concepts

## Decentralized identity

### Decentralized identifiers and verifiable credentials

The protocol implements the W3C’s standards (recommendations) for _Decentralized Identifiers_ (DIDs) [[10]](#ref10) and the _Verifiable Credentials Data Model_ (VCs) [[11]](#ref11).

The DID is a new type of identifier that enables verifiable, decentralized digital identity. DIDs are URIs that associate a DID subject (e.g., a person, organization, thing, data model, abstract entity, etc.) with a DID document allowing trustable interactions associated with that subject. DIDs have been designed so that they may be decoupled from centralized registries, identity providers, and certificate authorities. Specifically, while other parties might be used to help enable the discovery of information related to a DID, the design enables only the controller of a DID to prove control over it without requiring permission from any other party.

The VCs are global uniformed provable claims associated with the subject of the DID. They are cryptographically secure, privacy-respecting, tamper-evident and machine verifiable. They can be used to build universally verifiable presentations, which can also be cryptographically verified.

Verifiable credentials are provided by _credential issuers_—i.e., centralized or decentralized third parties—asserting certain facts about the DID owner. Verifiable credentials are consumed by _verifiers_ using the concepts and data models for _presentation exchange_. Verifiers ensure that the credential presentation is signed with the subject’s DID, it is signed by a trusted Issuer, it is not expired and it is not revoked.

### Growr approach to Self-sovereign credit record

The prevalence of strong social ties in the Global South enables the creation of self-sovereign digital identities without undergoing formal KYC procedures. By leveraging the _web of trust_,decentralized social identities such as Nostr [[12]](#ref12), or other similar concepts, these identities can be uniquely linked to each individual by relying on a network of credential issuers, instead of a single authority.

The Growr protocol relies on a new type of open and global decentralized identity built using DIDs and VCs that we call the _self-sovereign credit record (SSCR)_. The SSCR is intended to represent a borrower's unique global identity and financial record, storing various general-purpose and protocol-specific verifiable credentials based on the borrower’s on-chain activity, trusted off-chain data, peer vouching, financial health metrics, and others.

The SSCR contains both hard information (facts such as credit score and history, debt-to-income ratio, bank account verification, and business financial indicators) and soft information (such as endorsement, community membership, and self-declared business plans) that are used in the credit risk assessment.

## Lending and borrowing

### A brief history of debt

The concept of lending and borrowing is probably as old as the Sumer civilization around 3500 BC [[5]](#ref5). However, this often brought social tension—a significant part of the farmers would become over-indebted and be forced to sell their kids into debt slavery. Due to this fact, jubilees (cancellations of all debts) were often initiated by the rulers.

After the advent of coinage, banking and lending money against interest emerged as a business activity. This however often led to usury, or lending money at unreasonably high rates of interest out of the formal institutions, which was naturally considered sinful by most religions and outlawed by many states throughout history. Still, this practice continues today around the world, especially in communities with high informality and without access to financial services [[13]](#ref13).

In the Middle Ages, the notion of _interesse_ (from which “interest” originally comes) began to be accepted as a non-usurious compensation for the profit a merchant would have made, had they placed it in some profitable investment.

### Modern banking and financial inclusion

In modern banking, a loan is given to a borrower against interest and fees, which highly depend on the local context. Today, most countries have regulations on maximum interest rates. In Islamic banking where interest (riba) is forbidden, productive financing is provided through risk-sharing instruments.

However, even with regulated interest rates, the price of banking services is high, especially for half of the world’s population who lives on less than $6.85 per day [[14]](#ref14). This is mostly due to the cost of distribution, as banks traditionally rely on physical infrastructure, as well as due to information asymmetry, which limits the appetite of banks to lend to informal micro-enterprises and leads to credit rationing.

To assess borrower risk, banks use the services of credit bureaus—private companies or government agencies that collect data about borrowers from various sources. But people without prior credit history may find themselves trapped in a loophole as banks may not be willing to serve them at all. In the end, being poor becomes very expensive because the financially excluded easily fall prey to loan sharks with usurious conditions.

### Informal financial groups

Informal or semi-formal community financial groups (such as rotating savings and credit associations, village savings and loan associations, savings and credit cooperative societies and many other varieties) have existed for hundreds and even possibly thousands of years. They remain the primary way to save and borrow for the population in the Global South that does not have access to formal financial institutions. However, these groups remain disconnected from the global financial system and suffer from bad practices and physical cash security.

### Microfinance

Microfinance has emerged as an alternative to banking, as a large-scale, businesslike provision of financial services to the poor. Microfinance institutions (MFIs) usually lend money to large groups of people in dense regions, in a minimally subsidized way. To monitor and manage multiple borrowers, MFIs rely on a combination of reputation, knowledge of the client, collateral, cosigners, and enforceable contracts.

Although it has its roots in the Middle Ages, microfinance was reinvented in a scalable model in the late 1970s. Witnessing extreme poverty and a deadly famine in his country Bangladesh, Professor Muhammad Yunus came up with the noble vision to provide microcredit—and later more financial services—to poor communities, in a fair and sustainable manner, and help them out of poverty [[17]](#ref17).

However, over the last decades, there has been a significant deviation from this original purpose, with many MFIs changing their focus from social impact to profit and replicating the narrative but not the good practices. In some well-publicized cases, MFIs have contributed to increasing poverty rather than decreasing it.

### Decentralized lending protocols

Since 2020, an increasing number of decentralized borrowing and lending protocols have been emerging fast in the decentralized finance (DeFi) space. They aim to fundamentally reinvent the financial infrastructure, enabling people to transact with each other globally, securely and in a permissionless manner.

While most of the activity in the space is outside of the Bitcoin ecosystem, projects such as Tropykus and Sovryn built on Bitcoin’s side-chain Rootstock (RSK) are promising to bring decentralized lending to Bitcoin.

Decentralized finance protocols still target mostly advanced users and let them lend or borrow digital assets without going to a centralized intermediary. Users deposit digital assets into liquidity pools, which become funds that the protocol can lend out to other users. Decentralized finance protocols aim to automate lending and would not be willing to assess individual borrowers. That is why they require collateral. This means that the on-chain assets of the borrower are used to secure a loan. The borrower provides the asset to secure the loan, and if the borrower defaults on the loan, the lender can take possession of the asset and sell it to cover the loss. Moreover, they often require over-collateralization, i.e. the value of locked assets as collateral must significantly exceed the loan amount. Currently, decentralized finance usage is higher in developed markets and by institutional investors [[18]](#ref18).

### Growr approach to Open and transparent credit data

The Growr protocol approaches lending differently. The protocol aims at providing instant unsecured loans based on risk assessment and verifiable credentials, instead of requiring on-chain collateral. It provides an open credit record model, which also preserves the privacy of the borrowers through a self-sovereign identity, instead of relying on risk data locked within proprietary databases.

A large percentage of the global population remains with limited access to credit due to immigration, lack of credit history or due to negative reporting to credit bureaus in case of late bills—even when the invoice was never received by the debtor [[19]](#ref19). In contrast to the traditional credit bureaus, the protocol puts the users in control of their data by storing their credit record in “their own pocket” without dependence on any central authority or intermediary. This way, the protocol aims at enabling borrowers to build a credit record based on alternative and relevant data sources, such as trusted organizations, financial health metrics, and peer vouching.

Borrowers collect credentials into their self-sovereign credit record, originators use these credentials to better assess creditworthiness, and trusted parties are incentivized by the protocol to provide the credentials.

The credit records are open and global in nature, so they enable communities to combine their identities. Digital capital providers leveraging this identity and credit record infrastructure can apply flexible fine-grained investment criteria based on the available credentials. They can utilize the community’s reputation and guarantees from its supply chain partners to provide under-collateralized financing for micro-loans. As the community accumulates digital capital, it can use it as collateral to access even more financing at better rates.

## Growr approach to Bitcoin as a capital rail

First, Bitcoin provides a sound monetary foundation. It is the perfect store of value for long-term capital accumulation, which cannot be inflated or seized by governments or adversaries. It’s fully open and censorship-resistant in nature, which allows anyone to participate directly without the need to rely on intermediaries, creating a platform for building financial services outside of the traditional system.

Second, the Lightning network enables low-cost instant and global transfer of value—in bitcoin or fiat-pegged digital assets. This way, capital from anywhere in the world can reach even the most distant community directly, avoiding unnecessary costs.

Third, solutions such as federated Chaumian mints [[20]](#ref20) enable the creation of local circular economies based on bitcoin, based on community custody of self-sovereign digital identities, bitcoin and other digital assets. Bitcoin mints connected to the Lightning network make it possible for informal financial groups to become digital micro-banks and empower their members with a full set of financial services.

Fourth, smart contracts on Bitcoin side-chains enable global digital capital infrastructure and automated pooling of funds by capital providers, matching their investment criteria to community projects. Moreover, using side-chains, communities can start issuing debt similar to sovereign bonds – similarly to what El Salvador plans to do with their “volcano bonds” on Liquid [[21]](#ref21) – that allow them to attract investors looking for liquid instruments.

## Growr approach to Nostr as a social layer

Creating a global peer-to-peer market poses challenges with regard to transparency and discoverability. The communities need to communicate openly to build trust with capital providers. Capital providers need to be able to find projects they could invest in, and follow their progress.

In a peer-to-peer model, the communication between the protocol participants must also be decentralized. Nostr provides the right tools to enable such communication:

- Growr projects automatically get a decentralized identity (npub), through which project-related communication is shared by the originators before, during and after attracting funding. Nostr becomes a social layer for signaling soft information, while the data on Growr represents hard facts.
- Capital providers are able to discover projects through both Growr’s built-in discoverability mechanism and through Nostr. They can use Nostr’s “zap” feature [[22]](#ref22) to instantly fund projects using Lightning micro-payments, enabling an open crowdfunding mechanism.
- Borrowers can use their existing Nostr identities to control their self-sovereign credit record, instead of having to manage additional identities and private keys.

<div style="page-break-after: always;"></div>
