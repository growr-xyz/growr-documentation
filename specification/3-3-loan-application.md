## Loan application

### Loan application with a phone

```mermaid
sequenceDiagram
    actor B as Borrower
    participant US as USSD Gateway
    participant GUS as Growr User service
    participant GSA as Growr Identity service
    participant GLS as Growr Loan service
    participant GVS as Growr Verification service
    participant GPS as Growr Project service

    B->>US: Dial USSD
    B->>+US: Initiate application process
    US->>B: Request confirmation
    B->>US: Confirm loan application
    US->>+GUS: Sends confirmation data
    deactivate US
    GUS->>+GSA: Request credentials data
    GSA->>-GUS: Return credentials presentation
    GUS->>+GLS: Present credentials to apply
    GLS->>+GVS: Request validation
    GVS->>GPS: Check project eligibility
    GVS->>-GLS: Validate credentials
    GLS->>GLS: Create a loan record
    GLS-->>-GUS: Approved loan
    GUS-->>-B: Send notification
```

Process steps:

1. A borrower dials a number to receive a USSD menu.
2. The user selects the "loan application" option from the menu.
3. The USSD shows the terms and conditions of the loan and prompts the borrower to provide confirmation.
4. The borrower confirms the loan application.
5. The USSD provider sends the data to the Growr User service.
6. Growr User service requests verifiable credentials stored in the borrower’s Growr SSCR agent.
7. Growr Identity service creates a credential presentation and returns it to the Growr User service.
8. Growr User service presents the credentials in front of the Growr Loan service to apply for a loan.
9. Growr Loan service requests credentials validation from the Growr Verification service.
10. Growr Verification service reads the project eligibility criteria from the Growr Project service.
11. Growr Verification service validates the credentials and verifies the eligibility of the farmer in front of the Growr loan service.
12. Growr Loan service creates a new record in the protocol’s Loans book.
13. Growr Loan service confirms that the loan is approved and created.
14. Growr User service sends an SMS notification to the borrower.

The key step of the process is the eligibility assessment performed by the Verification service. It includes the following checks:

- Verify that the borrower has presented all the necessary verifiable credentials required for the project
- Verify the validity of each credential:
- Verify that the credential presentation is signed with the borrower's identity
- Verify that the credential is signed by a trusted credential issuer
- Verify that the credential is not expired
- Verify that the credential is not revoked

<div style="page-break-after: always;"></div>
