# Payments
## On-chain (Growr)
In the on-chain payments model, all transactions are executed on-chain, including:
- Pool smart contract to Pond smart contract
- Pond smart contract to Pool smart contract
- Borrower account to Pond smart contract
- Pond smart contract to Borrower account

### Off-ramp (Growr to off-chain account)
Growr protocol will integrate with third-party bridges to enable direct payouts after loan disbursement and for withdrawal of investments from the lending pools. Those third parties will provide access to payment rails currently operated by traditional ﬁnancial providers (e.g., card rails, instant payments, ACHs, etc.).
### On-ramp (off-chain account to Growr)
Similarly, for the needs of depositing funds into the Growr lending pools by investors, and for the repayment of loans by the borrowers, the protocol will support integration with various on-ramp methods speciﬁc for each geography. We plan to utilize third-party services, including decentralized on-ramp networks.
## Off-chain (Custodian)
In the off-chain payment model, the payments between Lenders and Borrowers are settled by traditional payments providers (Payment Processors). The Payment Processor in Growr protocol is required to issue "proof-of-pay" credentials to attest the payments are settled. The Payment Processor might also faciliate the payments between Liquidity Providers and Lenders in case of off-chain pond funding.