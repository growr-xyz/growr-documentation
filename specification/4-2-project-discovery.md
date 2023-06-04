## Project discovery

### Project publishing

```mermaid
sequenceDiagram
  participant ps as Growr Project service
  participant ns as Growr Nostr service
  participant nr as Nostr relay

  Note over ps: Upon project activation...
  activate ps
  ps->>+ns: Register public project
  ns->>ns: Create and store key pair
  ns->>nr: Publish project profile
  ns-->>-ps: Return npub
  ps->>-ps: Update project
```

Process steps:

1. Growr Project service sends information to Growr Nostr service about a new public project.
2. Growr Nostr service generates a new pair public-private keys and stores it securely.
3. Growr Nostr service publishes a Nostr profile for the project through a Nostr relay.
4. Growr Nostr service returns the npub of the Nostr profile.
5. Growr Project service stores the npub address and updates the record of the respective project in the Project book.

### Project feed

```mermaid

```

Process steps:

1. TBD

### Project discovery

```mermaid

```

Process steps:

1. TBD

<div style="page-break-after: always;"></div>
