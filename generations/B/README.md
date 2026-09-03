# FlowForge AVA — Generation B

[← Main README](../../README.md) · [Architecture diagram](ARCHITECTURE.md)

**Status:** HISTORICAL  
**Meaning:** knowledge-base expansion + tool/agent prompt restructuring.

## Contents

- [What changed](#what-changed)
- [Architecture](#architecture)
- [Architectural significance](#architectural-significance)
- [Why it was not final](#why-it-was-not-the-final-generation)
- [Evidence boundary](#evidence-boundary)

## What changed

Generation B expanded the assistant's knowledge-oriented behavior and restructured how the main assistant and specialist tool/agent prompts were organized.

## Architecture

[Open the Generation B architecture →](ARCHITECTURE.md)

The diagram visualizes the supported separation between the visible assistant, knowledge/Q&A behavior, scheduling/CRM specialists and deterministic routing. It is a historical explanatory model, not a recovered n8n screenshot.

## Architectural significance

This generation strengthens the separation between:

- the visible conversational assistant;
- knowledge retrieval / Q&A behavior;
- specialist scheduling/CRM operations;
- deterministic workflow routing around those AI components.

## Why it was not the final generation

Later work continued refining prompts/tool contracts and, importantly, rejected generated replacement workflows that changed real topology rather than preserving the implementation.

## Evidence boundary

The project history supports the knowledge/prompt restructuring direction. Exact node-for-node differences must come from preserved workflow artifacts rather than being reconstructed from this summary alone.

Historical generation: no fake runtime demo/screenshot placeholders are created.
