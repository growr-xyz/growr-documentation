## Data services

### Credit record storage

_Credit record storage_ provides decentralized storage of the self-sovereign credit record (SSCR) of the users. Each record represents a unique global decentralized identity and contains general-purpose and protocol-specific verifiable credentials. The credentials data is encrypted and accessible only by the identity owner.

The SSCR contains both hard information (facts such as credit score and history, debt-to-income ratio, bank account verification, and business financial indicators) and soft information (such as endorsement, community membership, and self-declared business plans) that are used in the credit risk assessment.

Potential types of verifiable credentials to be stored in the SSCR include:

<table>
  <tr>
   <td><strong>Credential category</strong>
   </td>
   <td><strong>Type</strong>
   </td>
   <td><strong>Proof</strong>
   </td>
   <td><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>KYC
   </td>
   <td>hard
   </td>
   <td>identity
   </td>
   <td>proves a successfully passed KYC process (including AML/CFT risk check)
   </td>
  </tr>
  <tr>
   <td>Financial data
   </td>
   <td>hard
   </td>
   <td>creditworthiness
   </td>
   <td>shows the financial habits of the user, as well as the trends in his cash flow (eg. transaction history, products)
   </td>
  </tr>
  <tr>
   <td>Savings history
   </td>
   <td>hard
   </td>
   <td>creditworthiness
   </td>
   <td>proves the financial discipline of the user (eg. regular micro-payments)
   </td>
  </tr>
  <tr>
   <td>Credit history
   </td>
   <td>hard
   </td>
   <td>creditworthiness & trustworthiness
   </td>
   <td>proves the financial discipline of the user (eg. past loans from the protocol)
   </td>
  </tr>
  <tr>
   <td>Business activity
   </td>
   <td>hard
   </td>
   <td>creditworthiness
   </td>
   <td>proves past and future revenue (income statement, cash flow, balance sheet) 
   </td>
  </tr>
  <tr>
   <td>Ownership
   </td>
   <td>hard
   </td>
   <td>creditworthiness
   </td>
   <td>proves the ownership of assets required for achieving the goals (eg. land, machines, raw materials)
   </td>
  </tr>
  <tr>
   <td>Community membership
   </td>
   <td>soft
   </td>
   <td>reputation
   </td>
   <td>asserts the trust of the organization
   </td>
  </tr>
  <tr>
   <td>Social endorsement
   </td>
   <td>soft
   </td>
   <td>reputation
   </td>
   <td>asserts the trust of other protocol participants having a certain reputation level
   </td>
  </tr>
  <tr>
   <td>Financial health
   </td>
   <td>soft
   </td>
   <td>trustworthiness
   </td>
   <td>proves successfully passed financial education or mentoring
   </td>
  </tr>
</table>

### Local data services

Some of the Growr services require database collections storing editable and manageable data locally in the node. This data usually does not contain lending or funding events and is not required to be distributed in the network (eg. user registration and onboarding). The collections can be implemented in MongoDB or other NoSQL databases.

The Growr protocol’s local collections are:

- _Organizations_
- _Users_
- _Project investors_

### Distributed data services

For storing and distributing project lending and funding data, Growr is using Holepunch's Hyperbee, an append-only B-tree based on Hypercore. It provides a key-value data store that is both fast and efficient, making it good for storing large amounts of data in a decentralized network. Additionally, it supports peer-to-peer synchronization, allowing the data to be replicated across the network in a highly efficient and fault-tolerant manner.

In addition, read-only copies are created and contain aggregated data plus audit logs, sanitized from any personal-revealing data. This data is publicly exposed to ensure transparency in the network and to monitor its global impact. Those read-only copies are implemented as a Hyperswarm with published well-known Public Key and Topic.

The Growr protocol’s distributed data logs are:

- _Project book:_ enables the creation of new projects with strictly defined eligibility criteria and potential funding sources.
- _Loan book:_ enables the creation of loans after an eligibility check of the borrower against the requirements of a given project.
- _Funding book:_ stores information about all funding operations
- _Payment book:_ stores information about loan utilization, repayment and other payment events.

<div style="page-break-after: always;"></div>
