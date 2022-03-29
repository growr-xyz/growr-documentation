# Protocol Participants

## Layers
![Growr protocol layers](../images/growr-layers.svg)  

Growr is a DeFi protocol operating on several layers:
- The processes in **Liquidity layer** are related to provisioning of the necessary funds for the protocol operation. Liquidity Providers and Lenders are collaborating on this layer.
- The **Risk Management layer** is the key layer of the protocol, it's the "magic" of the protocol. All processes related to local scoring and assessment, and loan management are happening on this layer.
- The **Distribution** layer covers the processes of onboarding and providing Borrowers with access to the protocol.
- The **Payments** layer combines all payment processes that occurs across all layers.
- The processes for smart contract governance and fraud prevention are covered in the **Governance layer**.

There are different players operating on each protocol layer, as well as between layers. Overview of all participants is presented below:

![Protocol Layers & Participants](../images/growr-layers-participants.svg)

## Borrowers
**Borrowers** get easy access to fair loans. They apply for funds from ponds with matching risk requirements and repay the funds with added interest and/or fees.
Borrowers gradually receive better conditions for positive behavior and improved financial health. They will receive “cash back”-style rewards based on their improved financial health (i.e., regular loan repayment and proof of financial learning), as well as for referral of good Borrowers.

Borrowers can access the protocol via a Distributor in custodial model or via a decentralized App in non-custodial model.  
Borrowers usually operate on the *Distribution* layer.

## Distributors
### Custodial Model
**Distributors**, or also called **Last-mile Providers** or **Custodial Wallet Providers**, intermediates access to the protocol to a specific group of Borrowers in custodial model with a simple UX. Distributors can be regulated financial institutions/fintechs, merchants, employers, or others. We envision that some Distributors may even operate as decentralized entities (DAOs).  
The role of the Distributor is to onboard and vet the users into its own digital means (e.g., a mobile application) and then facilitate access to the protocol. In this model, the user will have their SSFI under the custody of the Distributor.  
Often, a Distributor might be the same as a Lender.

Distributors usually operate on the *Distribution* layer and interact with *Risk Management* layer. In some cases, they might also have a role in the *Payments* layer.

### Non-Custodial Model
The end-user access to the protocol might be also provided in a fully decentralized non-custodial model. In this scenario, the user can access the protocol directly or through an agent wallet (decentralized web app with connected self-managed SSFI).

## Lenders
**Lenders** facilitates the interaction with the protocol as they create and fund ponds using own funds or by borrowing from global pools. Lenders can be regulated financial service providers, local communities or even governments.

They will receive yield based on the pond profitability, and the pond yield will tend to be higher than the pool yield, rewarding the skin-in-the-game participation of the Lender.

Lenders operate on *Risk Management* and *Liquidity* layers.

## Liquidity Providers
**Liquidity Providers (LPs)** are global institutional investors and high-net-worth individuals (HNWIs) who provide funding to the lending pools in the protocol and then delegate the actual lending activity to the Lenders.

Liquidity Providers allocate capital to lending pools and get rewarded with yield based on the pool profitability. Generally, the global pool yield will tend to be lower that the pond yield due to the wholesale lending nature of pools.

Some Liquidity Providers could play a role of **Guarantor** to provide first-loss capital and cover for missing credentials certain specific borrower groups (e.g., women, employees, unemployed, community members, companies of a given chamber, etc.). Guarantors will deposit funds into a Safety Fund, from which certain ponds can claim money in case of payment incidents.

Liquidity Providers operate on *Liquidity* layer.

## Credential Issuers
**Credential Issuers** serves an important risk management role in the protocol. They are centralized or decentralized third parties that provide **verifiable credentials (VCs)** to protocol participants.

Credential Issuers will receive a fee for the credentials they are issuing to Borrowers and other participants.

Credential Issuers operate on *Risk Management* layer.

## Risk Assessors
Credit risk assessment is a crucial component of the Growr protocol. Due to the decentralized nature of the protocol, we envision a decentralized credit risk assessment process with several participants in it.

A key participant is the **Risk Assessor** who provides a verification result asserting that a given Borrower matches the eligibility criteria of a given pond.
  
The Risk Assessors could be "owned" by Lenders, Liquidity Providers or Distributors to ensure they can manage their own policies, or could be provided by third parties (even by TradFi players).

The Risk Assessor may play one or several of the roles below. For the execution of its service, the Risk Assessor is rewarded with a fee according to its usage.

Risk Assessors operate on *Risk Management* layer.

### Credential Verifier
Credential Verifiers consumes credential presentations and verify that the credentials are valid i.e. issued from trusted Issuer, not expired, and not revoked.

### Credit Risk Scoring
In case of a more sophisticated pond eligibility requirements, Risk Assessor might implement a module for additional credit assessment/scoring techniques, including scorecards, ML models, and others. The result of this additional assessment is as a credit score, which is then matched with the pond's credit score requirements.

The Credit Risk Scoring could also participate in the protocol as a standalone Credential Issuer. 

### Credit Risk Reviewer
**Risk Reviewers** are employed by a Risk Assessor (or the protocol itself) to review a loan application and interview the Borrower in order to generate additional confirmation or vouching credentials used to endorse her/him.

The Credit Risk Reviewers could also participate in the protocol as individual Credential Issuers.

## Payment Processor
Payment Processors facilitates the payment processes in the protocol by providing different off-chain payment services. On the one side, they can provide on-ramp and off-ramp services, and on the other side, they facilitate and settle fiat payments between:
- Borrowers and Lenders
- Lenders and Liquidity Providers
  
For more information, see [Off-Chain Payments section](../layer-payments/2-Offchain-Payments.md).

Payment Processors operate on *Payments* layer.

## Protocol Governance Board
For the first version of the protocol, we envision to begin with a more centralized governance. At a later stage, decentralization will be implemented through a governance token that will be progressively airdropped to the most active contributors based on a predefined scheme. The protocol will ultimately be governed by a **DAO**, whose members will be all the protocol stakeholders. Each stakeholder will have voting rights based on their contribution to the protocol development and governance.

The Protocol Governance Board covers activities related to smart contract governance and fraud prevention. For more information, see [Protocol Governance section](../layer-governance/2-Protocol-Governance.md).

Naturally, Protocol Governance Board operates on *Governance* layer.