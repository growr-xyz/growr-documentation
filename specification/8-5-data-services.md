## Data services

### Credit record storage

The _Credit record storage_ provides decentralized storage of the self-sovereign credit record (SSCR) of the users. Each record represents a unique global decentralized identity and contains general-purpose and protocol-specific verifiable credentials. The credentials data is encrypted and accessible only by the identity owner.

### Local data services

TBD - implementation + collections

### Distributed data services

For storing and distribution of project lending and funding data, Growr is using Holepunch's Hyperbee. It provides a key-value datastore that is both fast and efficient, making it good for storing large amounts of data in a decentralized network. Additionally, it supports peer-to-peer synchronization, allowing the data to be replicated across the network in a highly efficient and fault-tolerant manner.

The Growr protocol’s distributed data services are:

- _Project book:_ Enables the creation of new projects with strictly defined eligibility criteria and a funding source.
- _Loan book:_ Enables the creation of loans after an eligibility check of the borrower against a given project.
- _Funding book:_ Contains history of funding operations.
- _Payment book:_ Contains history of loan utilization, repayment and other related events. It supports the issuing of proof of positive credit history.
- _Read-only copies:_ Contains aggregated data plus audit logs of the above services, sanitized from any personal-revealing data. It is publicly exposed to ensure transparency in the marketplace and to monitor its global impact.

To implement those operational data books, the Growr protocol leverages Holepunch’s Hyperbee, an append-only B-tree based on Hypercore. The read-only copies are implemented as a Hyperswarm with published well-known Public Key and Topic.

<div style="page-break-after: always;"></div>
