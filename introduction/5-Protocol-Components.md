# Protocol Components

![Components](../images/components.svg)

Growr protocol ecosystem consists of the following components:
- **Core Protocol**. Growr protocol is a smart contract system for decentralized lending on top of blockchain. Initially, the protocol will be deployed on RSK mainnet (powered by the most secure network - Bitcoin) but we envision future multi-chain implementation of the protocol. The Growr protocol consists of set of smart contracts:
  * *Pool Factory* smart contract. Enables creation of new lending pools.
  * *Pool* smart contracts. Support deposit & withdrawal operations from its owner, enable ponds to apply for credit lines.
  * *Pond Factory* smart contract. Enables creation of new lending ponds.
  * *Pond* smart contracts. Support deposit & withdrawal operations from its owner, provide loan offers and enable users to apply for loans.
  * *Trusted Service Registry* smart contract. Supports verification of risk assessment results.
  * *Loan Registry* smart contract. Registers privacy-preserving history of loan repayment commitments, supports issuing of on-chain verifiable credentials. 
- **SSFI**. SSFI is a unique global decentralized identity storing various protocol-specific verifiable credentials. The SSFI is owned and managed by the user, and their data is cryptographically encrypted and stored in a secured storage.
- **Protocol Apps**. Custodial or non-custodial web and mobile applications, integrated with the protocol. Include:
  * *Borrowing Apps* (Distribution Apps). End-user web or mobile application for the Borrowers to onboard, collect credentials and apply for loans to the protocol. Such applications can be provided either by an independent last-mile financial service providers in a regulated custodial scenario, by local communities or as completely decentralized dApps providing the necessary access to the protocol.
  * *Lending Apps* (Liquidity Apps). dApps for lending pools and pond management. Those applications include creation of pools/ponds, depositing and withdrawal of funds, and monitoring utilization and profitability performance.
  * *Governance Apps*. dApps for protocol monitoring, changes implementation and fraud prevention.
- Integration with **Third-party services**.
  * *Credential issuing services*. Issue verifiable credentials asserting certain facts about the borrower.
  * *Credential verification services*. Verify that presented credentials are trusted and valid, and owned by the subject.
  * *Risk assessment services*. Perform credential verification, additional loan scoring and reviewing in order to assert borrowers' eligibility to receive a loan. 
  * *Credential storage services*. Securely store the credentials and the declarative details, part of borrower's SSFI.
  * *Payment services*. Cover various on-ramp, off-ramp services, and fiat settlement services.