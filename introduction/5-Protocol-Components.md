# Protocol Components

## Components Overview
![Components](../images/components.svg)

## Core Protocol 
**Growr core protocol** represents a global decentralized marketplace where Lenders publish their targeted loan offers with predefined conditions and eligibility criteria. It is implemented as a smart contract system on top of blockchain. The protocol will be deployed on RSK mainnet, powered by the most secure network - Bitcoin. The Growr protocol consists of set of smart contracts:
- *Pool Factory* smart contract. Enables creation of new lending pools.
- *Pool* smart contracts. Support deposit & withdrawal operations from its owner, enable ponds to apply for credit lines.
- *Pond Factory* smart contract. Enables creation of new lending ponds.
- *Pond* smart contracts. Support deposit & withdrawal operations from its owner, provide loan offers and enable users to apply for loans.
- *Trusted Service Registry* smart contract. Supports verification of risk assessment results.
- *Loan Registry* smart contract. Registers privacy-preserving history of loan repayment commitments, supports issuing of on-chain verifiable credentials. 

## SSFI
**SSFI** is a unique global decentralized identity storing various protocol-specific verifiable credentials. The SSFI is owned and managed by the user, and their data is cryptographically encrypted and stored in a secure data store. The SSFI includes a DID and set of verifiable credentials stored in secure encrypted storage.

## Protocol Apps
**Protocol Apps** are custodial or non-custodial web and mobile applications, integrated with the protocol. Include:
- *Borrowing Apps* (Distribution Apps). End-user web or mobile applications for the Borrowers to onboard, collect credentials and apply for loans to the protocol. Such applications can be provided either by an independent last-mile financial service providers in a regulated custodial scenario, or by local communities, or as completely decentralized dApps providing the necessary access to the protocol.
- *Lending Apps* (Liquidity Apps). dApps for lending pool and pond management. Those applications include creation of pools/ponds, depositing and withdrawal of funds, and monitoring utilization and profitability performance.
- *Governance Apps*. dApps for protocol monitoring, changes implementation and fraud prevention.

## Protocol Services
The Growr core protocol and applications is integrated with various internal or third-party services, covering mainly risk management functions. 
  * *Credential issuing services*. Issue verifiable credentials asserting certain facts about the borrower.
  * *Credential verification services*. Verify that presented credentials are trusted and valid, and owned by the subject.
  * *Credential storage services*. Securely store the credentials and the declarative details, part of borrower's SSFI.
  * *Payment services*. Cover various on-ramp, off-ramp services, and fiat settlement services.
To implement the above services, the protocol utilizes various building blocks from RSK Infrastructure Framework (RIF).
