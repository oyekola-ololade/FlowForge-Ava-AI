# FlowForge AVA — Multi-Agent Lead & Customer Operations System

FlowForge AVA is a production-oriented multi-agent portfolio system for WhatsApp lead handling. It demonstrates validation, intent handling, conversation memory, specialist-agent coordination, CRM and calendar actions, operational alerts, and human handoff.

> **Evidence status:** Verified build with limitations. The repository does not claim full production readiness, guaranteed reliability, measurable ROI, or verified client outcomes.

![n8n](https://img.shields.io/badge/n8n-workflow-EA4B71?style=flat-square)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4.1%20%2B%20GPT--5--mini-412991?style=flat-square)
![WhatsApp](https://img.shields.io/badge/WhatsApp-integration-25D366?style=flat-square)
![Airtable](https://img.shields.io/badge/Airtable-CRM-18BFFF?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)

---

## What problem it explores

Businesses can lose inbound WhatsApp leads when replies are slow, qualification is inconsistent, information is not written to the CRM, or a conversation reaches a point where a person should take over.

AVA explores how one visible assistant can coordinate focused backend agents while keeping human review and handoff available.

## What the checked-in workflow demonstrates

- WhatsApp-style webhook intake and payload validation
- Intent and metadata detection
- One orchestrator coordinating Q&A, scheduling, and CRM specialist agents
- Conversation memory and state-aware questioning
- Airtable lead creation and updates
- Google Calendar availability checks and event creation
- Human-handoff summarisation and admin alerts
- Explicit rules against invented pricing, ROI, and timelines
- Credential references removed from the public documentation

The workflow is inspectable at [workflow/flowforge-ava.json.json](workflow/flowforge-ava.json.json).

## Architecture

<p align="center">
  <img src="architecture.drawio.png" width="900" alt="FlowForge AVA architecture diagram">
</p>

## Workflow preview

<p align="center">
  <img src="workflow-preview.png" width="1000" alt="FlowForge AVA n8n workflow">
</p>

## Current flow

1. A WhatsApp message reaches the webhook.
2. The payload is validated and normalised.
3. Intent and conversation metadata are detected.
4. The AVA orchestrator reads memory and selects the next action.
5. A Q&A, scheduling, or CRM specialist is called when required.
6. Lead information can be written to Airtable.
7. Calendar availability can be checked before an event is created.
8. A conversation can be summarised and handed to a person with context.

## Demonstration

A recorded portfolio demonstration is embedded below:

https://github.com/user-attachments/assets/c8574ce2-5e4e-486c-840f-e153035ab1dd

The demonstration is evidence of the portfolio build; it is not evidence of a production client deployment or business results.

## Verified technology in the exported workflow

| Layer | Current repository evidence |
|---|---|
| Orchestration | n8n |
| Main agent model | OpenAI GPT-4.1 |
| Specialist-agent models | OpenAI GPT-5-mini |
| Messaging | WhatsApp-compatible webhook/integration flow |
| CRM/data | Airtable |
| Scheduling | Google Calendar |
| Handoff | Context summary and admin-alert path |

Earlier project iterations explored other model providers. The checked-in workflow export is the authority for the current public repository configuration.

## Engineering decisions

### One orchestrator, focused specialist agents

The visible AVA agent manages the conversation and delegates bounded work to Q&A, scheduling, and CRM agents. Each specialist has a narrow role and tool boundary.

### Deterministic checks around model behaviour

Code nodes handle payload extraction, intent flags, timezone defaults, restart detection, and handoff summarisation. The AI layer is not treated as the only source of control.

### Human handoff remains available

The system prepares a compact handoff record so a person can take control without losing the lead's recent context.

### Calendar confirmation is gated

The scheduling agent is instructed to check availability before creating an event and to return alternatives when the proposed time is unavailable.

## Known limitations

The current version prioritises orchestration and conversation behaviour. The following are not yet evidenced as complete production controls:

- Robust retry policies across every external API
- Circuit breakers and provider failover
- Complete monitoring, logging, and operational dashboards
- Load, security, and long-duration reliability testing
- Verified deployment at client scale
- Measured conversion or ROI outcomes

## Next verification work

1. Add repeatable test fixtures for new, returning, booking, failure, and handoff paths.
2. Add explicit retry and failure handling for every external integration.
3. Add execution logging and operational monitoring.
4. Run security and credential-boundary review.
5. Record results only after configured execution with realistic test data.

## Evidence boundary

This is a production-oriented portfolio build, not a claim of production readiness. “Production-ready” should be used only after realistic execution, error-path testing, security review, observability, deployment evidence, and sustained operating results exist.

---

Designed and engineered by **Oyekola Ololade**

AI Systems & Integration Engineer

- [LinkedIn](https://www.linkedin.com/in/ololade-oyekola-5b1797397/)
- [GitHub](https://github.com/oyekola-ololade)
- Email: oyekolaololade69@gmail.com
