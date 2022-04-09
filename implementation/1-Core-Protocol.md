# Core Protocol
The core protocol is based on smart contracts on the RSK chain that match supply and demand, connecting Liquidity Providers to Borrowers with their preferred risk profile. Each lending pool, each local pond, as well as each individual loan, are powered by smart contracts on RSK chain. The RSK smart contract network, protected by the Bitcoin network computing power and hashing mechanism, will ensure the security of the smart contracts and transactions. We foresee the initial currency of choice to be USD-denominated stablecoin such as RDOC.

The protocol implements the following smart contracts:
- **Pool Factory** smart contract. Enables creation of new lending pools. [in design phase]
- **Pool** smart contract. Supports deposit & withdrawal operations from its owner, enables ponds to apply for credit lines. [in design phase]
- **Pond Factory** smart contract. Enables creation of new lending ponds. [version 0.1 in testnet]
- **Pond** smart contract. Supports deposit & withdrawal operations from its owner, provides loan offers and enables users to apply for loans. [version 0.1 in testnet]
- **Trusted Service Registry** smart contract. Supports verification of pond's eligibility criteria. [version 0.1 in testnet]
- **Loan Registry** smart contract. Registers privacy-preserving history of loan repayment commitments, supports issuing of on-chain verifiable credentials. [in design phase]


For more details on the core protocol's architecture, please visit [Growr protocol's repo in Github](https://github.com/growr-xyz/growr-core-protocol/wiki).