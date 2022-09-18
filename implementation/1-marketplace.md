# Decentralized marketplace

The _decentralized marketplace_ is based on smart contracts on the RSK chain that match supply and demand, connecting _investors_ to _borrowers_ with their preferred risk profiles. Each lending pool, each project, as well as each individual loan, are powered by smart contracts on the RSK chain. The RSK smart contract network, protected by the Bitcoin network computing power and hashing mechanism, will ensure the security of the smart contracts and transactions. We foresee the initial currency of choice to be a USD-denominated stablecoin such as RDOC.

The protocol implements the following smart contracts:
- **Pool Factory** smart contract. Enables the creation of new lending pools. [in design phase]
- **Pool** smart contract. Supports deposit & withdrawal operations from its owner, and enables projects to apply for funds from a pool. [in design phase]
- **Project Factory** smart contract. Enables the creation of new lending projects. [version 0.3 in testnet]
- **Project** smart contract. Supports deposit & withdrawal operations from its owner, and provides loan offers and enables users to apply for loans. [version 0.2 in testnet]
- **Verification Service Registry** smart contract. Supports verification of borrower's eligibility for a given project. [version 0.3 in testnet]
- **Loan Registry** smart contract. Registers privacy-preserving history of loan repayment commitments, and supports issuing of on-chain verifiable credentials. [in design phase]

For more details on the core protocol's architecture, please visit [Growr protocol's repo on Github](https://github.com/growr-xyz/growr-core-protocol/wiki).

To test the protocol on RSK Testnet:
- ProjectFactory (PondFactory) : 0x6069A41Ac8d73b7aE193f4890db1E84Df28a6835
- VerificationRegistry : 0xA05A7F9f6aA39d37f3fcE95D4A4ad5D273c0Db6C
- xUSD token: 0x7237aD8910561B683c760A29246af14cAA52EEd2
- DOC token: 0x84DF2f71B3d47C70a34dCd1C6E56fCb3a0b87F3C
- WRBTC token: 0x4e66383618f48666706CcE9eaF5439f141935f58