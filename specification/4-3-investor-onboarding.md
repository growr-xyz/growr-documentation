## Investor onboarding

### Investor registration

See [User registration](#ref-2-3-ur)

### Project funding invitation

```mermaid
sequenceDiagram
  actor i as Investor
  participant ip as Investor portal
  participant is as Growr Investor service
  participant lp as Lending portal
  actor o as Originator

  alt Project is opened to investors
  i->>ip: Select a project
  i->>+ip: Request invitation
  ip->>-is: Request invitation
  activate is
  is->>is: Create investment intent
  is-->>-o: Notification
  o->>lp: View requests
  end
  o->>+lp: Send invitation
  lp->>-is: Send invitation
  activate is
  is->>is: Create/update investment intent
  is-->>-i: Notification
```

Process steps:

1. An investor reviews the projects through the Investor portal and selects one that is opened for investment.
2. The investor requests funding invitation for the selected project.
3. The Investor portal sends the request to Growr Investor service.
4. Growr Project investor service registers the investment funding intent with status REQUESTED.
5. Growr Project investor service sends an email notification to the originator.
6. An originator admin reviews the funding invitation requests in the Lending portal.
7. The originator sends an invitation for project funding to a given investor (with or without existing invitation request).
8. The Lending portal sends the request to Growr Investor service.
9. Growr Project investor service registers (or update if existing) the investment funding intent with status INVITED.
10. Growr Project investor service sends an email notification to the investor.

### Project funding commitment

```mermaid
sequenceDiagram
  actor i as Investor
  participant ip as Investor portal
  participant is as Growr Investor service
  actor o as Originator

  i->>ip: View funding invitation
  i->>+ip: Confirm invitation
  ip->>+is: Confirm investment intent
  is->>is: Update investment intent
  is->>is: Generate contract
  is->>-ip: Return contract
  ip->>-i: Present contract for signing
  i->>+ip: Sign contract
  ip->>+is: Provide signature
  is->>is: Update investment intent
  is-->>o: Notification
  is-->>-ip: Confirmation
  ip-->>-i: Confirmation
  Note over i: Ready to fund
```

Process steps:

1. An investor is invited to fund a project.
2. The investor confirms the funding invitation through the Investor portal, indicating the investment amount, funding source and wallet address.
3. The Investor portal sends the confirmation to Growr Investor service.
4. Growr Project investor service updates the investment intent with status CONFIRMED.
5. Growr Project investor service generates an investment contract between the investor and the originator.
6. Growr Project investor service sends the contract back to the Investor portal.
7. The investor downloads the contract from the Investor portal and reviews it.
8. The investor signs the contract.
9. The Investor portal sends the signed contract together with investor's signature to Growr Project investor service.
10. Growr Project investor service updates the investment funding intent with status SIGNED.
11. Growr Project investor service sends an email notification to the originator.
12. Response message.
13. Response message.

<div style="page-break-after: always;"></div>
