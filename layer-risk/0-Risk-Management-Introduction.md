# Loan Risk Management
Growr protocol introduces an innovative approach for decentralized credit risk management, designed to work equally efficient in both custodial and non-custodial model.

The approach follows several key principles.
## Responsibility split
Each participant in the ecosystem has a risk management role:
- **Credential Issuers** assert facts about the Borrowers in the form of credentials.
- **Credential Verifiers** validates the credentials.
- **Risk Assessors** orchestrate the risk assessment activities and confirms that a Borrower matches the loan requirements.
- **Trusted Registries** validate that credentials are issued by trusted Issuers and risk assessments are prepared by trusted Risk Assessors.
- **Pond Smart Contracts** take decision based on the input from the above-mentioned risk management service providers.
- **Lenders** distribute part of the profit with all participants to motivate them to properly execute their risk management functions.
- **Protocol Governance Board** decides which participants are trusted and excludes the ones that misbehave.
  
## Incentivization
Each participant is incentivized by the protocol to fairly fulfil its duties, as follows:
- With positive behavior in terms of regularly repaid loans, **Borrowers** increase their credit risk score. And better risk score translates to better lending conditions - increased amount limit and decreased interest rate.
- **Credential Issuers**, **Credential Verifiers** and **Risk Assessors** receive a fee for the services they provide. In case of poor execution of their risk management function, the respective participant is blacklisted from the protocol. In addition, risk management service providers might be required to stake protocol tokens as a guarantee for their fair participation.
- **Lenders** and **Liquidity Providers** are incentivized to ensure sufficient level of risk management in order to decrease the cost of default and respectively to increase their profit.
  
## Privacy-preservation
The loan information stored on-chain does not contain any personal data. In the future protocol implementation, we also envision the usage of zero-knowledge proof (ZKP) model, in which the SSFI address of the user is not revealed.

This concept is still in early stage and is under research at the moment. More details on data privacy will be provided in the next version of the protocol documentation.