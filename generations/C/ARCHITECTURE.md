# FlowForge AVA — Generation C Architecture

> **Status:** HISTORICAL RECONSTRUCTION · topology-preservation generation.

```mermaid
flowchart TD
    A[Inbound conversation] --> B[Existing validated workflow topology]
    B --> C[AVA orchestrator]
    C --> D[Q&A specialist/tool]
    C --> E[Scheduling specialist/tool]
    C --> F[CRM specialist/tool]
    D --> G[Return tool result]
    E --> G
    F --> G
    G --> H[Deterministic state / routing checks]
    H --> I[Human handoff / alert path]
    H --> J[Conversation response]

    X[Generated replacement workflow] -. rejected when it changed or simplified real topology .-> B
```

## Interpretation

Generation C is important because documentation/prompt improvements were constrained to preserve the real orchestration graph. Generated replacement workflows that changed or simplified the implementation were rejected rather than relabelled as the same system.
