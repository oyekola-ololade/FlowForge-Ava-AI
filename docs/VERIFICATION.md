# FlowForge AVA Verification Matrix

## Current classification

**Verified portfolio build with limitations.**

The checked-in workflow and recorded demonstration are evidence of a real implementation. They are not evidence of a production client deployment, guaranteed uptime, conversion lift, ROI, or complete production hardening.

## Evidence matrix

| Area | Current evidence | Status |
|---|---|---|
| Workflow structure | n8n export | Present |
| Architecture | repository diagrams + Mermaid docs | Present |
| Conversation orchestration | workflow export + recorded demo | Demonstrated |
| CRM integration design | Airtable nodes and tool contract | Present |
| Calendar flow | availability + event-creation nodes | Present |
| Human handoff | explicit route, summary, user/admin messages | Present |
| Error handling | error trigger, user fallback, admin alert | Present |
| HOT-lead path | priority fields + persisted-record lookup + admin alert nodes | Present; fresh branch-specific rerun pending |
| Repeated deterministic fixtures | not yet checked in | Pending |
| Provider-failure fixtures | not yet checked in | Pending |
| Long-duration reliability | no sustained run evidence | Not verified |
| Load/security testing | no current test evidence | Not verified |
| Production deployment | no public proof claimed | Not verified |

## Minimum regression suite to add

1. New lead with ordinary qualification path.
2. Returning lead with conversation memory.
3. Explicit human-handoff request.
4. Calendar request with available slot.
5. Calendar request with unavailable slot and alternatives.
6. CRM save with HOT priority.
7. CRM save with non-HOT priority.
8. AI/tool failure triggering safe fallback.
9. External messaging failure.
10. Replay/retry case verifying side-effect behavior.

## Release-sanitization gate

Before a workflow export is advertised as the canonical public file:

- remove credential objects and environment-specific credential IDs;
- remove private instance identifiers and reusable webhook identifiers;
- replace account emails, table/base IDs, group/chat destinations, private document URLs, and cached resource URLs with explicit placeholders;
- inspect Code-node strings for embedded secrets or private identifiers;
- parse the resulting JSON and import it into a clean n8n environment;
- confirm that sanitization did not break node connections or expressions.

## Claim boundary

Acceptable: **production-oriented portfolio system**, **multi-agent n8n implementation**, **recorded portfolio demonstration**, **implemented human-handoff and CRM/calendar paths**.

Not currently supported: **production-ready**, **client-scale reliability**, **guaranteed conversion improvement**, **measured ROI**, **24/7 operation**, or **production security certification**.
