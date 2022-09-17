<a name="ref-m5"></a># Loan Repayment

The loan repayment process depends on several project parameters:
- *Payment Model:* On-chain/Off-chain
- *Community Model:* Yes/No
- *Repayment model:* Fixed monthly schedule / Ad-hoc

In the *on-chain* payment model, the repayment transaction is executed on-chain through a transfer between the borrower and the project smart contract. In the *off-chain* payment model, the repayment transaction is settled by a traditional payment provider (payment processor) and it is recorded in the protocol after the *payment verification service* issue a "proof-of-pay" credential.

If the loan is *individual* (community model = no), each borrower repays only his/her loan(s) and any unpaid loans in the project remain in default. If the loan follows the *community model*, the unpaid loans are compensated by additional risk deposits, collected on top of the repaid loans.

If the loan has a *fixed repayment plan* the interest amount is predefined and the repayment amount (principal + interest) is split in several monthly installments. If the loan has a flexible *ad-hoc repayment* model, then the interest amount is a variable calculated based on the period between disbursement and repayment.

## On-chain Repayment

Below is a diagram that describes the process:

TBD

## Off-chain Repayment

Below is a diagram that describes the process:

TBD

<div style="page-break-after: always;"></div>