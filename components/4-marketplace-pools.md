# Pools

<a name="ref-c4"></a>

## Description

Projects can be funded in 2 ways – (1) directly by the project owner (usually - the lender) or (2) by applying for funds from a lending pool. The latter approach requires the creation of global lending pools that group projects with similar risk levels and financing conditions. The lending pools play the role of investment funds for the projects.

## Characteristics

 - *Owned by:* Protocol
 - *Funded by:* Investors / DeFi protocols
 - *Funding to:* Projects with similar risk levels and financing conditions
 - *Time period:* Unlimited
 - *Available amount:* Variable, depending on the funding operations
 - *Utilized amount:* Variable, depending on the project utilization
 - *Interest rate:* Fixed

## Implementation

The protocol has a *Pool Factory smart contract* that enables the creation of new pools combining projects with certain risk levels and financing conditions. This smart contract is controlled by Growr governance board (initially - Growr core developers) through a multi-sig account.
Pool Factory contract functions:
 - Create a pool
 - Destroy a pool

Each pool is created through the pool factory as a separate *Pool smart contract*. It enables investors to provide liquidity to the projects through those pools. The pool smart contracts are controlled by ... TBD.
Pool contract functions:
 - Deposit funds
 - Withdraw funds
 - Activate funding
 - Deactivate funding
 - Close

## Pool types

Pools may vary depending on the following specifics:
1. Funding
Each pool can attract liquidity in 2 ways - (1) direct deposits from investors or (2) integration with DeFi protocols.

<div style="page-break-after: always;"></div>
