# FlowForge AVA — Generation D Current Architecture

> **Status:** CURRENT PUBLIC IMPLEMENTATION GENERATION.

```mermaid
flowchart TD
    A[WhatsApp-style inbound webhook] --> B[Payload validation / normalization]
    B --> C[Intent + metadata + restart/handoff checks]
    C --> D[Conversation memory / session context]
    D --> E[AVA orchestrator]

    E --> F[Q&A specialist / knowledge tool]
    E --> G[Scheduling specialist / Calendar]
    E --> H[CRM specialist / Airtable]

    F --> I[Tool result]
    G --> I
    H --> I

    I --> J[Deterministic output / state checks]
    J --> K{Lead priority / next action}
    K -->|HOT / escalation| L[Persist + admin alert]
    K -->|Booking| M[Availability gate → event creation]
    K -->|Normal| N[Conversation response]

    J --> O{Human handoff requested / required?}
    O -->|Yes| P[Context summary + operator notification]
    O -->|No| N

    Q[n8n error trigger] --> R[Admin error alert / user fallback]
```

## Current visual evidence

- [`../../architecture.drawio.png`](../../architecture.drawio.png) — current architecture image.
- [`../../workflow-preview.png`](../../workflow-preview.png) — current n8n workflow screenshot.
- [`../../critical-paths.svg`](../../critical-paths.svg) — HOT-lead and human-handoff critical paths.
- recorded demo linked from the root [`README.md`](../../README.md).

These artifacts demonstrate the current portfolio build. They do not prove production deployment, SLA, ROI, or client-scale reliability.
