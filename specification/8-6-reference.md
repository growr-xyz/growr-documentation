## Reference

### Data structures

<table>
  <tr>
   <td><strong>Structure</strong>
   </td>
   <td><strong>Attribute(s)</strong>
   </td>
   <td><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>key
   </td>
   <td>Unique identifier
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>status
   </td>
   <td>DRAFT | ACTIVATED | DEACTIVATED | CLOSED
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>organizationId
<p>
userId</p>
   </td>
   <td>Information about who created the project
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>name
<p>
description</p>
   </td>
   <td>Descriptive attributes of the project
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>isPublic
   </td>
   <td>Whether the project is publicly discoverable or not
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>profileUrl
<p>
bannerUrl</p>
<p>
npub</p>
   </td>
   <td>Publishing attributes of the project
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>startDate
   </td>
   <td>Initial date of lending operations
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>endDate
   </td>
   <td>No new loans are accepted after this date
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>amount
<p>
currency</p>
   </td>
   <td>Total target amount and currency of the loans from the project 
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>eligibilityCriteria
   </td>
   <td>List of verifiable credentials and conditions required for loan approval
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>loanType
<p>
loanMinDuration</p>
<p>
loanMaxDuration</p>
<p>
loanMinAmount</p>
<p>
loanMaxAmount</p>
   </td>
   <td>Restrictive parameters for the loans from the project
   </td>
  </tr>
  <tr>
   <td>Project book
   </td>
   <td>isInviteOnly
   </td>
   <td>Whether the project requires an invitation to become an investor
   </td>
  </tr>
  <tr>
   <td>Project book > funding [ ]
   </td>
   <td>type
   </td>
   <td>BANK | ONCHAIN
   </td>
  </tr>
  <tr>
   <td>Project book > funding [ ]
   </td>
   <td>status
   </td>
   <td>ACTIVE | INACTIVE
   </td>
  </tr>
  <tr>
   <td>Project book > funding [ ]
   </td>
   <td>networkName
<p>
tokenName</p>
<p>
fundingAddress</p>
<p>
repaymentAddress</p>
   </td>
   <td>Details of the payment rail and currency
   </td>
  </tr>
  <tr>
   <td>Project book > funding [ ]
   </td>
   <td>terms
<p>
interestRate</p>
<p>
leverageFactor</p>
   </td>
   <td>Descriptive attributes of the funding source
   </td>
  </tr>
  <tr>
   <td>Project book > funding [ ]
   </td>
   <td>fundingMinAmount
<p>
fundingMaxAmount</p>
   </td>
   <td>Restrictive parameters for the project investments
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>projectKey
   </td>
   <td>Unique identifier of the project
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>fundingType
<p>
fundingNetwork</p>
<p>
fundingToken</p>
   </td>
   <td>Details of the payment rail and currency
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>paymentType
   </td>
   <td>INCOMING | OUTGOING
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>amount
   </td>
   <td>Amount of the payment
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>fundingAddress
   </td>
   <td>Project wallet address that received the investment (for incoming events)
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>repaymentAddress
   </td>
   <td>Project wallet address that initiated the repayment (for outgoing events)
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>investorAddress
   </td>
   <td>Wallet address of the investor
   </td>
  </tr>
  <tr>
   <td>Funding book
   </td>
   <td>proof
   </td>
   <td>Proof of the payment (trx id, invoice hash, etc.)
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>key
   </td>
   <td>Unique identifier of the loan
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>projectKey
   </td>
   <td>Unique identifier of the project
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>organizationId
   </td>
   <td>Unique identifier of the originator
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>userDid
   </td>
   <td>DID of the borrower
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>verifierDid
   </td>
   <td>DID of the credential verifier service
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>status
   </td>
   <td>DRAFT | APPROVED | DISBURSED | REPAID | DEFAULTED
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>type
   </td>
   <td>Type of the loan product
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>startDate
<p>
endDate</p>
<p>
duration</p>
   </td>
   <td>Loan duration parameters
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>interestRate
<p>
disbursementFee</p>
<p>
cashBackRate</p>
<p>
gracePeriod</p>
   </td>
   <td>Loan financial parameters
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>currency
   </td>
   <td>Currency of the loan
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>contractAmount
   </td>
   <td>Amount to be disbursed to the borrower
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>interestAmount
   </td>
   <td>Total interest amount
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>commitmentAmount
   </td>
   <td>Total amount to be repaid (contractAmount + interestAmount)
   </td>
  </tr>
  <tr>
   <td>Loan book
   </td>
   <td>repaidAmount
   </td>
   <td>Total repaid amount
   </td>
  </tr>
</table>

### Services

<table>
  <tr>
   <td><strong>Service</strong>
   </td>
   <td><strong>Action(s)</strong>
   </td>
   <td><strong>Description</strong>
   </td>
  </tr>
  <tr>
   <td>Identity (SSCR)
   </td>
   <td>findByDid
   </td>
   <td>Get mapping between user id and DID
   </td>
  </tr>
  <tr>
   <td>Identity (SSCR)
   </td>
   <td>createWallet
   </td>
   <td>Create a new SSCR with DID
   </td>
  </tr>
  <tr>
   <td>Identity (SSCR)
   </td>
   <td>getVC
   </td>
   <td>Claim a new verifiable credential
   </td>
  </tr>
  <tr>
   <td>Identity (SSCR)
   </td>
   <td>createVCPresentation
   </td>
   <td>Create a presentation of a verifiable credential
   </td>
  </tr>
  <tr>
   <td>Credential issuing
   </td>
   <td>issueVC
   </td>
   <td>Issue a verifiable credential
   </td>
  </tr>
  <tr>
   <td>Credential verification
   </td>
   <td>validateVC
   </td>
   <td>Validate a verifiable credential
   </td>
  </tr>
  <tr>
   <td>Organization
   </td>
   <td>findById
<p>
findByUser</p>
   </td>
   <td>Get organizations by different filters
   </td>
  </tr>
  <tr>
   <td>Organization
   </td>
   <td>createOrganization
   </td>
   <td>Create a new organization
   </td>
  </tr>
  <tr>
   <td>Organization
   </td>
   <td>addMember
   </td>
   <td>Add user to an organization
   </td>
  </tr>
  <tr>
   <td>User
   </td>
   <td>findById
<p>
findByOrganization</p>
   </td>
   <td>Get users by different filters
   </td>
  </tr>
  <tr>
   <td>User
   </td>
   <td>addUser
<p>
registerBorrower</p>
<p>
registerOriginator</p>
<p>
registerInvestor</p>
   </td>
   <td>Add a new user
   </td>
  </tr>
  <tr>
   <td>User
   </td>
   <td>updateUser
   </td>
   <td>Update details of a given user
   </td>
  </tr>
  <tr>
   <td>User
   </td>
   <td>getOTP
<p>
validateOTP</p>
<p>
setPIN</p>
<p>
validatePIN</p>
<p>
loginByEmail</p>
<p>
loginBySocial</p>
   </td>
   <td>Actions required for the different types of user authentication
   </td>
  </tr>
  <tr>
   <td>Project
   </td>
   <td>findByKey
<p>
findByOrganization</p>
<p>
findByAddress</p>
<p>
findPublic</p>
   </td>
   <td>Get projects by different filters
   </td>
  </tr>
  <tr>
   <td>Project
   </td>
   <td>createProject
   </td>
   <td>Create a new project
   </td>
  </tr>
  <tr>
   <td>Project
   </td>
   <td>updateProject
<p>
modifyProjectParams</p>
<p>
addProjectFunding</p>
   </td>
   <td>Update different project attributes
   </td>
  </tr>
  <tr>
   <td>Project
   </td>
   <td>activateProject
<p>
deactivateProject</p>
   </td>
   <td>Enable or pause the lending activities within a project 
   </td>
  </tr>
  <tr>
   <td>Loan
   </td>
   <td>findByKey
<p>
findByProject</p>
<p>
findByOrganization</p>
<p>
findByUser</p>
   </td>
   <td>Get loans by different filters
   </td>
  </tr>
  <tr>
   <td>Loan
   </td>
   <td>applyForLoan
   </td>
   <td>Request loan approval
   </td>
  </tr>
  <tr>
   <td>Loan
   </td>
   <td>signLoan
   </td>
   <td>Sign loan application
   </td>
  </tr>
  <tr>
   <td>Loan
   </td>
   <td>updateLoan
   </td>
   <td>Update loan details upon loan disbursement or repayment
   </td>
  </tr>
  <tr>
   <td>Project investor
   </td>
   <td>findByProject
<p>
findByInvestor</p>
   </td>
   <td>Get project 
   </td>
  </tr>
  <tr>
   <td>Project investor
   </td>
   <td>requestInvitation
<p>
acceptInvitation</p>
<p>
rejectInvitation</p>
   </td>
   <td>Actions executed by the investor during the project investment setup
   </td>
  </tr>
  <tr>
   <td>Project investor
   </td>
   <td>inviteInvestor
<p>
approveInvestor</p>
<p>
rejectInvestor</p>
   </td>
   <td>Actions executed by the originator during the project investment setup
   </td>
  </tr>
  <tr>
   <td>Funding
   </td>
   <td>findByKey
<p>
findByProject</p>
   </td>
   <td>Get funding events by different filters
   </td>
  </tr>
  <tr>
   <td>Funding
   </td>
   <td>fund
   </td>
   <td>Create a new funding event
   </td>
  </tr>
  <tr>
   <td>Funding
   </td>
   <td>refund
<p>
revert</p>
   </td>
   <td>Create a new repayment event
   </td>
  </tr>
  <tr>
   <td>Funding
   </td>
   <td>detect
   </td>
   <td>Process detected payment and call a method for the new event
   </td>
  </tr>
  <tr>
   <td>Payment
   </td>
   <td>findByLoan
<p>
findByAddress</p>
   </td>
   <td>Get loan payments by different filters
   </td>
  </tr>
  <tr>
   <td>Payment
   </td>
   <td>addDisbursement
<p>
confirmDisbursement</p>
<p>
addRepayment</p>
<p>
confirmRepayment</p>
   </td>
   <td>Create and confirm payment events
   </td>
  </tr>
  <tr>
   <td>Network 
<p>
(Bitcoin,</p>
<p>
Lightning,</p>
<p>
Rootstock)</p>
   </td>
   <td>createWallet
   </td>
   <td>Create a new private-public key pair
   </td>
  </tr>
  <tr>
   <td>Network
   </td>
   <td>createListener
   </td>
   <td>Create a new on-chain listener for a given network and address
   </td>
  </tr>
  <tr>
   <td>Network
   </td>
   <td>getPayments
   </td>
   <td>Get all on-chain payments detected by a given listener
   </td>
  </tr>
  <tr>
   <td>Nostr
   </td>
   <td>createProfile
   </td>
   <td>Create Nostr profile
   </td>
  </tr>
  <tr>
   <td>Nostr
   </td>
   <td>createPost
<p>
createDM</p>
   </td>
   <td>Post different kinds of messages
   </td>
  </tr>
  <tr>
   <td>Nostr
   </td>
   <td>getFeed
<p>
getZapRequests</p>
<p>
getZaps</p>
   </td>
   <td>Get a list of different events associated with a given profile
   </td>
  </tr>
</table>

<div style="page-break-after: always;"></div>
