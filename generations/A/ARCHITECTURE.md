# FlowForge AVA — Generation A Architecture

> **Status:** HISTORICAL RECONSTRUCTION FROM PROJECT LINEAGE · not the current workflow graph.

```mermaid
flowchart TD
    A[Inbound lead message] --> B[Basic validation / intent handling]
    B --> C[Lead qualification]
    C --> D[Lead state / CRM update]
    C --> E[Appointment intent]
    E --> F[Availability / booking action]
    D --> G[Response]
    F --> G
    G --> H{Human takeover needed?}
    H -->|Yes| I[Handoff / operator notification]
    H -->|No| J[Continue conversation]
```

## Interpretation

Generation A captures the earliest supported lead/appointment-bot architecture in the reconstructed project history. It is an explanatory historical model, not a claim that the exact current node graph already existed at this stage.
