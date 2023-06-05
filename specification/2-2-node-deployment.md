## Growr node deployment

There are 2 main options for Growr node deployment:

- Self-hosted by originators or capital providers
- Managed by the Growr team

### Self-hosting

In progress

### Managed service

In progress

### Organization setup

Once the Growr node is deployed, the first thing to do is to create an organization with one initial user.

```mermaid
sequenceDiagram
    actor A as Node Operator
    participant Nop as Node Operator portal
    participant Org as Growr Organization service
    participant User as Growr User service

    A->>+Nop: Configure new organization
    Nop->>Org: Forward request
    activate Org
    Org->>Org: Create organization
    Org->>+User: Request org admin creation
    User->>User: Create user
    User-->>-Org: User created
    Org-->>-Nop: Org and user created
    Nop-->>-A: Confirmation message
```

Process steps:

1. Growr node operator setups a new organization through the Node Operator portal.
2. The portal routes the request to the Growr Organization service.
3. Growr Organization service creates a new record in the Organizations collection.
4. Growr Organization service sends a request to the Growr User service to create an initial admin user for the new organization.
5. Growr User service creates a new record in the Users collection.

<div style="page-break-after: always;"></div>
