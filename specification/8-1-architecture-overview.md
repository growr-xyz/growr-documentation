# ARCHITECTURE OVERVIEW

## Overview

The design of Growr architecture includes the following considerations:

- The _identity system_ should allow users to prove their identity without exposing their personal data. It should also allow the users to decide whether to control their data by themselves or to use a custodial service.
- The _storage system_ should enable secure and reliable storage of the data gathered from all lending and funding activities. To provide transparency of the protocol, tamper-proof cryptographically verified data should be easily and openly distributed.
- The _communication system_ should facilitate the outreach and engagement of borrowers, originators and investors. It should enable secure and verifiable exchange of lending documents and signatures.

The following diagram provides a high-level overview of Growr functional architecture.

![Architecture](../images/growr-architecture.svg)

_Growr protocol_ implements a global decentralized micro-lending marketplace as a P2P network of Growr nodes. Each _Growr node_ represents a package of open-source components and a set of lending projects. It enables originators to publish projects with predefined conditions and eligibility criteria, and borrowers to apply and get financing using credentials from their self-sovereign credit record. It also enables capital providers to fund projects either by accessing the Growr node of an originator directly, or by running their own node.

Growr architecture provides the opportunity to pack the applications and services in few options, based on the deployment requirements and specifics. There are several deployment blueprints for Growr node depending on the use cases, for example: self-hosted originator node, cloud-hosted originator node or cloud-hosted investor node. The backend services can be packed as a single docker image and can be included in different configurations to run all or few services per deployment target.

The Growr nodes communicates between each other in 2 ways. The first option is through a Discovery service, using the TCP Gossip transport protocol. The second option is through replication of the distributed data across the network, using Holepunch's Hyperbee and Hyperswarm protocols.

<div style="page-break-after: always;"></div>
