# FlowForge AVA — Generation D

[← Main README](../../README.md) · [Current architecture](ARCHITECTURE.md)

**Status:** **CURRENT PUBLIC IMPLEMENTATION GENERATION**

## Contents

- [What this generation contains](#what-this-generation-contains)
- [Architecture](#architecture)
- [Current architecture decisions](#current-architecture-decisions)
- [Verification boundary](#current-verification-boundary)
- [Media](#media)

## What this generation contains

Generation D is the current AVA export plus the cleaned public evidence/documentation layer.

Current repository evidence includes:

- normalized current n8n workflow export: `../../workflow/flowforge-ava.json`;
- main AVA orchestrator;
- conversation memory and restart/handoff state;
- Q&A, appointment and CRM specialist-agent/tool structure;
- Airtable lead persistence/upsert behavior;
- Google Calendar availability/event operations;
- HOT/WARM/COLD prioritization logic;
- human-handoff summarization + admin alert paths;
- error-trigger/admin alert and user fallback paths;
- current architecture diagram;
- workflow screenshot/preview;
- critical-path SVG;
- genuine recorded portfolio demo linked from the main README;
- security and verification documentation.

## Architecture

[Open the Generation D architecture →](ARCHITECTURE.md)

The architecture page maps the current entrypoint, session state, AVA orchestrator, Q&A/scheduling/CRM specialists, deterministic state checks, lead-priority actions, human handoff and error path. It also links to the actual current architecture image, workflow screenshot and critical-path SVG.

## Current architecture decisions

- one visible conversational entrypoint coordinates focused specialist tools/agents;
- deterministic code/IF nodes own exact routing/state checks where practical;
- session context is preserved for multi-turn operation;
- human handoff is explicit rather than an AI-only conversational promise;
- calendar booking is gated on availability;
- failures should become visible through user fallback and/or operator alerts;
- unsupported client, ROI, uptime, SLA and production claims are excluded from the safe knowledge boundary.

## Current verification boundary

Implementation structure and a real demo exist. Fresh repeatable fixtures are still required for stronger claims around:

- HOT lead persistence and alert behavior;
- repeated/replayed side effects;
- explicit human handoff and destination failure;
- calendar available/unavailable cases;
- CRM/provider/tool failure;
- sustained reliability/load/security/monitoring.

## Media

Generation D already has real current media, so no empty placeholders are created.

- `../../architecture.drawio.png`
- `../../workflow-preview.png`
- `../../critical-paths.svg`
- recorded demo link in `../../README.md`

These prove the demonstrated portfolio build only; they do not prove client-scale production operation.
