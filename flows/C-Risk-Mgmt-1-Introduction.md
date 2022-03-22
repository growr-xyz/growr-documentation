# Risk Management Introduction
Growr protocol introduces an innovative approach for decentralized credit risk management, designed to work equally efficient in both custodial and non-custodial model.  
The approach follows several key principles.
## Responsibility split
Each participant in the ecosystem has a risk management role:
- Credential Issuers assert facts about the Borrowers in the form of credentials.
- Credential Verifiers validates the credentials.
- Risk Assessors orchestrate the risk assessment activities and confirms that a Borrower matches the loan requirements.
- Registry Smart Contracts validate that risk assessment is prepared by trusted Rusk Assessors.
- Pond Smart Contracts take decision based on the input from the above-mentioned risk management service providers.
- Lender distributes part of the profit with all participants to motivate them to properly execute their risk management functions.
- Protocol Governance Board decides which participants are trusted and excludes the one that misbehave.
## Incentivization
Each participant is incentivized by the protocol to fairly fulfil its duties, as follows:
- With positive behaviour in terms of regularly repaid loans, Borrowers increase their credit risk score, and better risk score provides them with better lending conditions - increased amount limit and decreased interest rate.
- Credential Issuers, Credential Verifiers and Risk Assessors receive a fee for the services they provide; in case of poor execution of their risk management function, the respective participant is blacklisted from the protocol. In addition, risk management service providers might be required to stake protocol tokens as a collateral to their fair participation.
- Lenders and Liquidity Providers are incentivized to ensure sufficient level of risk management in order to decrease the cost of default and respectively to increase their profit.
## Privacy-preservation
The loan information stored on-chain does not contain any personal data. In the future protocol implementation, we also envision the usage of zero-knowledge proof (ZKF) model, in which even the SSFI address of the user could not be revealed.  
TBD-description