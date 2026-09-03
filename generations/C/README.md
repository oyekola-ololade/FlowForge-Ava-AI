# FlowForge AVA — Generation C

[← Main README](../../README.md) · [Architecture diagram](ARCHITECTURE.md)

**Status:** HISTORICAL  
**Meaning:** prompt/tool rework while preserving real workflow topology.

## Contents

- [Why this generation matters](#why-this-generation-matters)
- [Architecture](#architecture)
- [Direction](#direction)
- [Decision retained](#decision-retained-into-current-generation)
- [Evidence boundary](#evidence-boundary)

## Why this generation matters

Generation C records an important engineering constraint: generated replacement workflows were rejected when they changed or simplified the actual topology instead of improving the existing implementation faithfully.

## Architecture

[Open the Generation C architecture →](ARCHITECTURE.md)

The diagram preserves the topology-first decision: prompts/tools could be refined, but replacement graphs that changed the actual implementation were not accepted as equivalent evidence.

## Direction

The accepted work focused on:

- prompt/tool behavior refinement;
- preserving the real orchestration graph;
- keeping specialist roles bounded;
- improving human-handoff and operational behavior without pretending a replacement graph was the same system.

## Decision retained into current generation

**Implementation topology is evidence.** Documentation or generated redesigns cannot silently replace the actual checked-in workflow and then be described as the same implementation.

## Evidence boundary

This record supports the topology-preservation decision and prompt/tool rework direction. It does not invent exact workflow diffs where surviving artifacts have not been mapped.

Historical generation: no fake runtime demo/screenshot placeholders are created.
