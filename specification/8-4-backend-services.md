## Back-end services

### Overview

The backend of Growr has microservices architecture based on _MoleculerJS_. Besides the traditional features, such as load balancing, service discovery, and fault tolerance, MoleculerJS has the ability to distribute messages across multiple nodes using the TCP gossip protocol and allows easy switching of the transport technology depending on the use case.

Below is a table containing a summarized list of the back-end services:

<table>
  <tr>
   <td><strong>Group</strong>
   </td>
   <td><strong>Service</strong>
   </td>
   <td><strong>Data storage</strong>
   </td>
  </tr>
  <tr>
   <td>Access
   </td>
   <td>API gateway
   </td>
   <td>-
   </td>
  </tr>
  <tr>
   <td>Access
   </td>
   <td>Discovery
   </td>
   <td>-
   </td>
  </tr>
  <tr>
   <td>Identity
   </td>
   <td>Organization
   </td>
   <td>local
   </td>
  </tr>
  <tr>
   <td>Identity
   </td>
   <td>User
   </td>
   <td>local
   </td>
  </tr>
  <tr>
   <td>Identity
   </td>
   <td>Identity
   </td>
   <td>Local / External
   </td>
  </tr>
  <tr>
   <td>Identity
   </td>
   <td>Credential issuing
   </td>
   <td>-
   </td>
  </tr>
  <tr>
   <td>Identity
   </td>
   <td>Credential verification
   </td>
   <td>-
   </td>
  </tr>
  <tr>
   <td>Financing
   </td>
   <td>Project
   </td>
   <td>distributed
   </td>
  </tr>
  <tr>
   <td>Financing
   </td>
   <td>Loan
   </td>
   <td>distributed
   </td>
  </tr>
  <tr>
   <td>Financing
   </td>
   <td>Investor
   </td>
   <td>local
   </td>
  </tr>
  <tr>
   <td>Financing
   </td>
   <td>Funding
   </td>
   <td>distributed
   </td>
  </tr>
  <tr>
   <td>Payment
   </td>
   <td>Payment
   </td>
   <td>local
   </td>
  </tr>
  <tr>
   <td>Payment
   </td>
   <td>Bitcoin
   </td>
   <td>external (L1)
   </td>
  </tr>
  <tr>
   <td>Payment
   </td>
   <td>Lightning
   </td>
   <td>external (L2)
   </td>
  </tr>
  <tr>
   <td>Payment
   </td>
   <td>Rootstock
   </td>
   <td>external (L1)
   </td>
  </tr>
  <tr>
   <td>Publishing
   </td>
   <td>Nostr
   </td>
   <td>external (Nostr)
   </td>
  </tr>
</table>

### API gateway

The _API gateway_ controls access to the back-end services. It exposes APIs using GraphQL, providing a flexible and efficient way to retrieve data from the services.

### Discovery service

The _Discovery service_ ensures the discoverability of Growr nodes and the possibility to use other node services (for example, Verification or Issuing) using the TCP Gossip transport protocol.

### Identity services

The main _Identity service_ (also called _SSCR Agent_) is based on Self Sovereign Identity (SSI) standard. SSI is designed for managing identity data in a decentralized, secure way. It supports the creation, management, and sharing of verifiable credentials that can be used to prove identity attributes without revealing sensitive personal information.

In the current protocol implementation, the _Identity service_ is implemented as a custodial service that operates the self-sovereign credit record (SSCR) of the user with his permission. It controls the DID of the borrower and his/her verifiable credentials.

The _Credential issuing service_ is responsible for issuing verifiable credentials for given borrowers based on data received or verified by the originator or other third parties. The _Credential verification service_ is responsible for the validation of presentations of verifiable credentials and assessing the eligibility of a given user to apply for a loan. To be trusted by all network participants, those two services have well-known DIDs and deployment addresses.

The _Organization service_ and the _User service_ are responsible for the registration and management of the users of the frontend applications in the node. They read and write data to database collections having the same name.

### Financing services

The _Project service:_ is responsible for creating and managing the lending projects. It reads and writes data to the _Project book_.

The _Loan service:_ controls the approval, creation, utilization and repayment of loans. It reads and writes data to the _Loan book_.

The _Funding service:_ is responsible for project funding and project repayment operations. It reads and writes data to the _Funding book_.

The _Project investor service:_ provides onboarding and contract management services for project investors. It reads and writes data to a database collection having the same name.

### Payment services

Growr protocol implements a set of services with payment management functions.

The main _Payment service_ is responsible to track all payments related to activities in the protocol. It reads and writes data to the _Payment book_.

The _Bitcoin service_, _Lightning service_ and _Rootstock service_ provide integration with the respective payment networks. They are responsible for wallet management, transaction execution and transaction listening.

### Publishing services

Growr protocol implements publishing through _NOSTR_. It is an innovative protocol designed to create censorship-resistant global social networks. Its tamper-proof design is based on cryptographic keys and signatures, relying on a network of distributed relays to ensure messages are sent in a robust and censorship-resistant manner.

Growr _Nostr service_ is responsible for creating a public Nostr profile and posting various types of messages on behalf of this profile.

### Supporting services

The backend of the Growr protocol contains also a set of supporting services that are not directly exposed via APIs but are used internally by the other services. They include:

- Database management, MongoDB
- Append-only log, Hyperbee and Hyperswarm
- Private key management, NDS
- Authentication, Passport
- JSON rule engine
- Email & SMS

<div style="page-break-after: always;"></div>
