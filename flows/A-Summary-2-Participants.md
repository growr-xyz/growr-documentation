# Protocol Participants
## Borrowers
**Borrowers** get easy access to fair loans. They apply for funds from ponds with matching risk requirements and repay the funds with added interest and/or fees.
Borrowers gradually receive better conditions for positive behavior and improved ﬁnancial health. They will receive “cash back”-style rewards based on their improved ﬁnancial health (i.e., regular loan repayment and proof of ﬁnancial learning), as well as for referral of good Borrowers.  
Borrowers can access the protocol via a Distributor in custodial model or via a decentralized App in non-custodial model.
## Distributors
### Custodial Model
**Distributors**, or also called **Custodial Providers**, intermediates access to the protocol to a speciﬁc group of Borrowers in custodial model with a simple UX. Distributors can be regulated financial institutions/fintechs, merchants, employers, or others. We envision that some Distributors may even operate as decentralized entities (DAOs).  
The role of the Distributor is to onboard and vet the users into its own digital means (e.g., a mobile application) and then facilitate access to the protocol. In this model, the user will have their SSFI under the custody of the Distributor.  
Often, a Distributor might also play the role of a Lender.
### Non-Custodial Model
The end-user access to the protocol might be also provided in a fully decentralized non-custodial model. In this scenario, the user can use the protocol directly or through a decentralized web app using his/her self-managed SSFI.
## Lenders
**Lenders** facilitates the interaction with the protocol as they create and fund ponds using own funds or by borrowing from global pools. 
They will receive yield based on the pond proﬁtability, and the pond yield will tend to be higher than the pool yield, rewarding the skin-in-the-game participation of the lender.
## Liquidity Proviers
**Liquidity Providers (LPs)** are institutional investors and high-net-worth individuals (HNWIs) who provide funding to the lending pools in the protocol and then delegate the actual lending activity to the Lenders.  
Liquidity Providers allocate capital to lending pools and get rewarded with yield based on the pool profitability. Generally, the global pool yield will tend to be lower that the pond yield due to the wholesale lending nature of pools.  
Some Liquidity Providers could play a role of **Guarantor** to provide first-loss capital and cover for missing credentials certain specific borrower groups (e.g., women, employees, unemployed, community members, companies of a given chamber, etc.). Guarantors will deposit funds into a Safety Fund, from which certain ponds can claim money in case of payment incidents.
## Credential Issuers
**Credential Issuers** serves an important risk management role in the protocol. They are centralized or decentralized third parties that provide **verifiable credentials (VCs)** to protocol participants.  
Credential Issuers will receive a fee for the credentials they are issuing to Borrowers and other participants.
## Risk Assessors
Credit risk assessment is a crucial component of the Growr protocol. Due to the decentralized nature of the protocol, we envision a decentralized credit risk assessment process with several participants in it.  
A key participant is the **Risk Assessor** who provides a verification result assesting that a given Borrower matches the eligibility criteria of a given pond. For this service, the Risk Assessor is rewarded with a fee according to its usage.  
The Risk Assessors could be "owned" by Liquidity Providers or Distributors to ensure they can manage their own policies, or provided by third parties (even by TradFi players).  
The Risk Assessor may play one or several of the roles below.
### Credential Verifier
Credential Verifiers consumes credential presentations and verify that the credentials are valid i.e. issued from trusted Issuer, not expired, and not revoked.
### Credit Risk Scoring
In case of a more sophisticated pond eligibility requirements, Risk Assessor might implement a module for additional credit assessment/scoring techniques, including scorecards, ML models, and others. The result of this additional assessment is as a credit score, which is then matched with the pond's credit score requirements.  
The Credit Risk Scoring could also participate in the protocol as a standalone Credential Issuer. 
### Credit Risk Reviewer
**Risk Reviewers** are employed by a Risk Assesor (or the protocol itself) to review a loan application and interview the Borrower in order to generate additional confirmation or vouching credentials used to endorse her/him.  
The Credit Risk Reviewers could also participate in the protocol as individual Credential Issuers.
## Payment Processor
Payment Processors facilitates the payment processes in the protocol by providing different off-chain payment services.
### Custodian
With this role, the Payment Processor facilitates the payments between the Lenders and the Borrowers in the custodial model and issues VCs to attest the payments are settled. The Payment Processor might also faciliate the payments between Liquidity Providers and the Lenders in case of off-chain pond funding.
### Off-ramp (Growr to account)
Growr protocol will integrate with third-party bridges to enable direct payouts after loan disbursement and for withdrawal of investments from the lending pools. Those third parties will provide access to payment rails currently operated by traditional ﬁnancial providers (e.g., card rails, instant payments, ACHs, etc.).
### On-ramp (account to Growr)
Similarly, for the needs of depositing funds into the Growr lending pools by investors, and for the repayment of loans by the borrowers, the protocol will support integration with various on-ramp methods speciﬁc for each geography. We plan to utilize third-party services, including decentralized on-ramp networks.
## Protocol Governance Board
For the ﬁrst version of the protocol, we envision to begin with a more centralized governance. At a later stage, decentralization will be implemented through a governance token that will be progressively airdropped to the most active contributors based on a predeﬁned scheme. The protocol will ultimately be governed by a **DAO**, whose members will be all the protocol stakeholders. Each stakeholder will have voting rights based on their contribution to the protocol development and governance.  
The Protocol Governance Board covers activities related to smart contract governance and fraud prevention. 
