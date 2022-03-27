# Protocol Overview
## Layers
![Growr protocol layers](../images/growr-layers.png)  

Growr is a DeFi protocol operating on several layers:
- The processes in **Liquidity layer** are related to provisioning of the necessary funds for the protocol operation. Liquidity Providers and Lenders are collaborating on this layer.
- The **Risk Management layer** is the key layer of the protocol, it's the "magic" of the protocol. All processes related to local scoring and assessment, and loan management are happening on this layer.
- The **Distribution** layer covers the processes of onboarding and providing Borrowers with access to the protocol.
- The **Payments** layer combines all payment processes that occurs accross all layers.
- The processes for smart contract governance and fraud are covered in the **Governance layer**.

For more information on the protocol participants and their role, see [Participants](./A-Summary-2-Participants.md).

For more information on the processes on each layer, see the following sections.

## Custodial Model
In custodial implementation model, the Borrowers access the protocol via Distributor app, provided by regulated last-mile financial service providers. The self-sovereign financial profile and connected credentials are also under custody. Payments are managed by off-chain custodian (payment processor).  
![Growr Custodial model](../images/growr-custodial.png)

## Non-Custodial Model
The non-custodial model allows full decentralization of the protocol. Borrowers access the protol using a dApp having their wallet connected and all translactions are executed on-chain.  
![Growr Non-Custodial model](../images/growr-non-custodial.png)