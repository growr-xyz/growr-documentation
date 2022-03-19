# Loan Repayment
## Off-chain Custodian Model
TBD-description
## On-Chain Model
Loans in Growr protocol are designed to be repaid on-chain through regular installments.
TBD-diagram
Borrowers are allowed to repay an amount different than the installment. 
- If repaid amount = installment amount -> normal installment repayment
- If repaid amount < installment amount -> partial installment repayment
- If repaid amount > installment amount -> normal + partial installment repayment
- If repaid amount = remaining loan amount -> final loan repayment
- If repaid amount > remaining loan amount -> final loan repayment + returning back the difference

