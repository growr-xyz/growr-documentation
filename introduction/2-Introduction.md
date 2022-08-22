# Protocol overview

## Problem

Today, a quarter of the world’s adult population does not have an account [[1]](#ref1). In some countries in the developing world, financial exclusion is as high as 90%. Most of the unbanked population does not have a typical “job”—they are smallholder farmers, micro-entrepreneurs or self-employed [[2]](#ref2). They are all facing a staggering financing gap of over US$5 trillion per year [[3]](#bookmark=id.zb1wngbhfl3j). In addition, only a third of adults worldwide are financially literate, and as a result, can easily fall prey to moneylenders and loan sharks [[1]](#bookmark=id.bfrz3agnh7dk).

Traditional financial services actors are not economically incentivized to solve those problems. The distribution costs of banks to deliver their services to remote areas and informal populations have led to low adoption of their services in the developing world. Moreover, one of the main reasons for the high global financing gap is the credit rationing due to information asymmetry [[4]](#bookmark=id.4hli6wam7ywa). Microfinance has emerged as a solution to the financial inclusion problem, providing the necessary financing to poor entrepreneurs in the form of microcredit. Originally operating mostly in the form of NGOs, the sector has progressively commercialized and its image as an agent of poverty alleviation has been tarnished through research [[5]](#bookmark=id.9l1qiem2c68u) and public scandals due to the lack of transparency and other bad practices [[6]](#bookmark=id.xvjl6ajilywm).

Bitcoin, its second-layer Lightning network and other projects are focused on democratizing access to accounts, payments and remittances through the use of open-source protocols and software. They have emerged as a viable financial inclusion solution for unbanked communities [[7]](#bookmark=id.3hmckpk728yb). At the same time, the typical decentralized finance (DeFi) protocols—including the ones that are part of the Bitcoin ecosystem such as Tropykus [[8]](#bookmark=id.lsirj56u4q03) or Sovryn Zero [[9]](#bookmark=id.br7l6xhssmuh)—require over-collateralization, which is out of the reach of the unbanked. Due to the pseudonymous nature of the users of Bitcoin, there is currently no widely available solution to provide unsecured credit on the network or its upper layers.


## Solution

Previous research exists on the promise of using blockchain technology as a solution to the information asymmetry and credit rationing problem [[10]](#bookmark=id.l3piqohtidr4). Lenders have abstained from offering higher prices to riskier borrowers to avoid adverse selection. Instead, they can facilitate self-selection by low-risk micro-enterprises who are ready to signal their credit history on-chain, while high-risk ones will not be able to do so and will remain served by traditional microfinance. A similar approach exists in online peer-to-peer lending where screening through soft information such as the number of friend endorsements and the loan purpose, is relatively more important when evaluating lower-quality borrowers [[11]](#bookmark=id.1jw74478exu5).

Decentralized finance offers several benefits such as high efficiency through programmability, open permissionless access and transparency, despite many current shortcomings [[12]](#bookmark=id.tk1wki9kuvwj). Therefore, the availability of on-chain information signaling from borrowers can be an excellent source of risk assessment by decentralized lending protocols.

By using this approach, the _Growr protocol_ aims to be a bridge between two worlds—decentralized finance and microfinance—while addressing each one’s challenges. The protocol enables micro-entrepreneurs to receive instant productive loans based on their self-sovereign credit record without the need for over-collateralization. In contrast to traditional microfinance, the protocol creates an open and global lending marketplace that connects borrowers to both traditional and decentralized lenders, enforcing fair competition for pricing and fully transparent deployment of capital down to each micro-loan.

The protocol aims to contribute to addressing the global financial inclusion problem by providing open access to basic financial services:



* Borrowers, represented by self-employed, micro-businesses, smallholder farmers and the communities of which they are members, are provided with access to fair productive micro-loans to grow their businesses. In addition, they receive help and promotion of financial health and good business practices.
* Suppliers and buyers that support the development of sustainable local economies have revenue growth, as well as easier and streamlined agreements with a cooperative instead of with each member individually.
* Lenders in the marketplace benefit from real-world yield generation opportunities on a global scale, and in addition, they get complete transparency of the impact of each unit of capital they invest.

The key elements of the protocol are:


* _Self-sovereign credit record (SSCR):_ a global digital self-sovereign identity, owned and managed by the user. The SSCR stores protocol-specific verifiable credentials based on the user’s financial health metrics, on-chain activity, and trusted off-chain data, and enables decentralized credit risk assessment and reduction of information asymmetry.
* _Decentralized micro-lending marketplace:_ an open and global lending marketplace on top of Bitcoin and its side-chain Rootstock (RSK) [[13]](#bookmark=id.g3kb6c4k2ufd) that connects borrowers with lenders who publish their targeted offers with predefined conditions and eligibility criteria.
* _Financial health incentivization:_ the protocol promotes the usage of tools and education that help borrowers develop financial health habits and rewards the roles that issue and consider such credentials.

More details about the protocol mechanics are provided in the following sections.

