# FlowForge AVA — Generation B Architecture

> **Status:** HISTORICAL RECONSTRUCTION FROM PROJECT LINEAGE.

```mermaid
flowchart TD
    A[Inbound conversation] --> B[Validation / routing]
    B --> C[Visible AVA assistant]
    C --> D[Knowledge / Q&A path]
    C --> E[Scheduling specialist]
    C --> F[CRM specialist]
    D --> G[Knowledge response]
    E --> H[Availability / booking]
    F --> I[Lead create / update]
    G --> J[Conversation response]
    H --> J
    I --> J
    J --> K{Human handoff?}
    K -->|Yes| L[Context summary + operator path]
    K -->|No| M[Continue session]
```

## Interpretation

Generation B records the expansion from a simpler lead/appointment bot toward a visible assistant coordinating knowledge, scheduling and CRM responsibilities. Exact node-level deltas remain governed by preserved workflow evidence rather than this explanatory reconstruction.
