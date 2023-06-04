## Data services

### Credit record storage

The _Credit record storage_ provides decentralized storage of the self-sovereign credit record (SSCR) of the users. Each record represents a unique global decentralized identity and contains general-purpose and protocol-specific verifiable credentials. The credentials data is encrypted and accessible only by the identity owner.

### Local data services

Some of the Growr services require database collections storing editable and manageable data locally in the node. This data usually does not contain lending or funding events and is not required to be distributed in the network (eg. user registration and onboarding). The collections can be implemented in MongoDB or other NoSQL database.

The Growr protocol’s local collections are:

- _Organizations_
- _Users_
- _Project investors_

### Distributed data services

For storing and distribution of project lending and funding data, Growr is using Holepunch's Hyperbee, an append-only B-tree based on Hypercore. It provides a key-value datastore that is both fast and efficient, making it good for storing large amounts of data in a decentralized network. Additionally, it supports peer-to-peer synchronization, allowing the data to be replicated across the network in a highly efficient and fault-tolerant manner.

In addition, read-only copies are created and contain aggregated data plus audit logs, sanitized from any personal-revealing data. This data is publicly exposed to ensure transparency in the network and to monitor its global impact. Those read-only copies are implemented as a Hyperswarm with published well-known Public Key and Topic.

The Growr protocol’s distributed data logs are:

- _Project book:_ enables the creation of new projects with strictly defined eligibility criteria and potential funding sources.
- _Loan book:_ enables the creation of loans after an eligibility check of the borrower against the requirements of a given project.
- _Funding book:_ stores information about all funding operations
- _Payment book:_ stores information about loan utilization, repayment and other payment events.

<div style="page-break-after: always;"></div>
