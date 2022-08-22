# Protocol architecture

## Overview

The following diagram provides a high-level overview of the protocol components.

![Architecture](../images/growr-architecture.svg)

## Decentralized micro-lending marketplace

The decentralized micro-lending marketplace is where lenders publish their loan offers with predefined conditions and eligibility criteria, and borrowers apply to get financing based on the automatic matching of these criteria with the credentials in their self-sovereign credit record. It is implemented as a smart contract system on top of Rootstock (RSK) mainnet, a side-chain secured by approximately 66% of Bitcoin’s miners as of August 2022 [[22]](#ref22).

The Growr protocol consists of a set of smart contracts:

* _Pool factory_: enables the creation of new liquidity pools for senior tranche funding.
* _Pool_: supports deposit & withdrawal operations from its owner and enables projects to apply for credit lines.
* _Project factory_: enables the creation of new projects with credit line parameters and eligibility criteria.
* _Project_: supports deposit & withdrawal operations from its owner, provides loan offers and enables users to apply for micro-loans within the approved credit limit and eligibility criteria.
* _Trusted service registry_: supports verification of risk assessment results.
* _Loan registry_: registers privacy-preserving history of loan repayment commitments and supports issuing of on-chain verifiable credentials.

## Self-sovereign credit record storage

The _self-sovereign credit record (SSCR)_ is a unique global decentralized identity containing general-purpose and protocol-specific verifiable credentials. The SSCR is owned and managed by the user, and the credential data is encrypted and kept in decentralized storage.

## Protocol apps

Protocol apps are custodial or non-custodial web and mobile applications, integrated with the protocol, including:

* _Borrowing (distribution) apps._ End-user web or mobile applications for the Borrowers to onboard, collect credentials and apply for loans to the protocol. Such applications can be provided either by an independent financial service provider in a regulated custodial scenario, by local communities, or as a completely decentralized app providing the necessary access to the protocol.
* _Lending apps._ Decentralized applications for lending pool and project management. Those applications include the creation of pools and projects, depositing and withdrawing of funds, and monitoring utilization and profitability performance.

## Protocol services

The Growr core protocol and applications are integrated with various internal or third-party services, covering mainly risk management functions.

* _Credential issuing services._ Issue verifiable credentials asserting certain facts about the borrower.
* _Credential verification services._ Verify that the presented credentials are trusted and valid and owned by the subject.
* _Credential storage services._ Securely store the credentials and the declarative details, part of the borrower’s SSCR.
* _Payment services._ Cover various on-ramp, off-ramp services, and fiat settlement services. To implement the above services, the protocol utilizes various building blocks from RSK Infrastructure Framework (RIF).
