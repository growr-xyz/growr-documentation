# Project Closure

<a name="ref-m8"></a>

Projects can be closed either by their owner (only when there are no active loans) or automatically by the *Project Factory smart contract* when the following conditions are met:

- The project has expired (no more loans are approved)
- All approved loans are either repaid or expired
- The overdue repayment period (if configured) has ended

Upon project closure and in the case of an *on-chain payment model*, the *Project smart contract* calculates amounts and repays the project balance as described in the diagram below:

```mermaid
 sequenceDiagram
    participant PRFC as Project Factory contract
    participant PRC as Project contract
    participant POC as Pool contract
    participant Project Owner
    participant Borrower
    PRFC->>PRC: Request closure
    activate PRC
    PRC->>PRC: Check closing conditions are met
    PRC->>PRC: Calculate repayment amounts
    opt Pool funding?
        PRC->>POC: Transfer outstanding senior tranche principal and interest
    end
    opt Project repayment ratio > threshold?
        loop For each borrower
            PRC->>Borrower: Transfer outstanding risk deposits proportionally
            opt Individual loan repaid on-time?
                PRC->>Borrower: Transfer "cash-back" reward
            end
        end
    end
    PRC->>Project Owner: Transfer outstanding junior tranche principal and interest
    PRC-->>PRFC: "Ready for closure"
    deactivate PRC
    PRFC->>PRC: Destroy the project
 ```

<div style="page-break-after: always;"></div>