# FlowForge AVA Workflow Export

This folder contains the checked-in n8n implementation evidence for FlowForge AVA.

## Current file

`flowforge-ava.json` is the normalized filename for the current exported workflow generation.

The export demonstrates the implemented orchestration structure, including:

- inbound webhook handling and payload validation;
- intent and metadata detection;
- conversation memory management;
- AVA orchestration with specialist Q&A, scheduling, and CRM agent tools;
- Airtable lead persistence;
- calendar availability checking and event creation;
- human-handoff summarisation and admin alerting;
- fallback/error paths;
- HOT/WARM/COLD lead-priority handling.

## Public-use warning

The checked-in implementation has historically contained environment-specific node configuration and credential references such as internal resource IDs, cached account labels, webhook identifiers, and integration destinations. Those references are **not reusable credentials** and should not be treated as portable configuration.

Before importing or republishing the workflow:

1. Inspect every credential reference and resource identifier.
2. Replace environment-specific Airtable, Google, messaging, calendar, webhook, document, and destination values.
3. Use fresh test credentials.
4. Keep the workflow inactive until configured tests pass.
5. Never commit actual API tokens, OAuth secrets, private customer data, or reusable production credentials.

A dedicated release-sanitization pass is still required before this file should be advertised as a portable public template.

## Evidence boundary

This export is evidence of a real portfolio implementation. It is **not** evidence of production deployment, client-scale reliability, measured conversion performance, or production security.

See [`../docs/VERIFICATION.md`](../docs/VERIFICATION.md), [`../docs/CRITICAL_PATHS.md`](../docs/CRITICAL_PATHS.md), and [`../SECURITY.md`](../SECURITY.md).
