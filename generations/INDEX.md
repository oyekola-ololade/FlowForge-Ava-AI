# FlowForge AVA — Generation Archive

This directory preserves the implementation lineage without inventing semantic version numbers.

- [Generation A](A/README.md) — original lead / appointment bot structure.
- [Generation B](B/README.md) — knowledge-base expansion and tool/agent prompt restructuring.
- [Generation C](C/README.md) — prompt/tool rework while preserving the actual workflow topology after generated replacement workflows were rejected.
- [Generation D](D/README.md) — current AVA export, architecture/demo evidence and buyer-proof cleanup.

## Archive rule

Historical generations document what changed and why. They do **not** receive empty demo/screenshot placeholders. Generation D already has genuine media in the repository.

## Cross-generation decisions retained in current AVA

- WhatsApp-style conversational entrypoint;
- persistent/session context;
- specialist agents/tools rather than one monolithic prompt;
- explicit human-handoff route;
- lead priority driving different operational behavior;
- booking gated on sufficient identity/context and calendar availability;
- tool/API failure should surface a fallback rather than silently continue.

The checked-in current workflow is the authority for current public implementation claims.