# Growr Components Overview

The following diagram provides a high-level overview of the protocol components.

![Architecture](../images/growr-architecture.svg)

The **Decentralized micro-lending marketplace** is where lenders publish their loan offers with predefined conditions and eligibility criteria, and borrowers apply to get financing based on the automatic matching of these criteria with the credentials in their self-sovereign credit record. It is implemented as a smart contract system on top of Rootstock (RSK) mainnet. More details are available in the [Projects section](#ref-c2), [Loans section](#ref-c3) and [Pools section](#ref-c4)

The **Self-sovereign credit record (SSCR)** is a unique global decentralized identity containing general-purpose and protocol-specific verifiable credentials. More details are available in the [Self-sovereign Credit Record section](#ref-c1).

The **Protocol apps** are custodial or non-custodial web and mobile applications, integrated with the protocol. **Borrowing (distribution)** apps are end-user web or mobile applications for the borrowers to onboard, collect credentials and apply for loans to the protocol. Such applications can be provided either by an independent financial service provider in a regulated custodial scenario, by local communities, or as a completely decentralized app providing the necessary access to the protocol. **Lending** apps are web applications for the management of lending pools and lending projects.

The marketplace and the applications are integrated with various internal or third-party services, covering mainly risk management functions, such as **credential issuing services**, **credential verification services** (more details are available in the [Credential Verification section](#ref-c5)), **credential storage services** and **payment verification services** (more details are available in the [Payment Verification section](#ref-c6)).

<div style="page-break-after: always;"></div>