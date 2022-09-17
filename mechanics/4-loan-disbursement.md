<a name="ref-m4"></a># Loan Disbursement

Loans can be disbursed in two ways depending on the *payment model* parameter of the project. 

## On-chain Disbursement

In the *on-chain* payment model, the disbursement transaction is executed on-chain immediately after loan creation (as part of the Loan Approval process).

## Off-chain Disbursement

In the *off-chain* payment model, the disbursement transaction is settled by a traditional payment provider (payment processor) and it is recorded in the protocol after the *payment verification service* issue a "proof-of-pay" credential.

Below is a diagram that describes the process:

```mermaid
sequenceDiagram
    participant Borrowing App
	participant PVS as Payment Verification service
    participant PRC as Project contract
    Note over Borrowing App: Custodial distribution app or Self-custody wallet
    Note over PRC: ...Loan with off-chain payments is approved
    Borrowing App->>PVS: Check payment document status
    activate PVS
        PVS->>PVS: Verify external transaction
        PVS->>PVS: Issue and sign a verification result
        alt payment is cancelled?
            PVS->>PRC: Provide result for cancelled payment
            activate PRC
            PRC->>PRC: Validate signature
            PRC->>PRC: Cancel a loan
            PRC-->>PVS: "Loan cancelled"
            deactivate PRC
            PVS-->>Borrowing App: "Loan cancelled"
        else payment is executed?
            PVS->>PRC: Provide result for executed payment
            activate PRC
            PRC->>PRC: Validate signature
            PRC->>PRC: Mark loan as disbursed
            PRC-->>PVS: "Loan disbursed"
            deactivate PRC
            PVS-->>Borrowing App: "Loan disbursed"
        end
    deactivate PVS
```

The *payment verification service* performs the verification of an external financial transaction. Depending on the payment channel, the verification may include one of the following:

- Confirming the existence of a blockchain transaction in another protocol
- Check payment document status through an integration with an invoice validation service
- Check transaction status through integration with a payment processor (a card provider or a bank)

<div style="page-break-after: always;"></div>