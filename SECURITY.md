# Security Policy

FlowForge AVA is a portfolio implementation. Do not use the public repository configuration for real customer data or production credentials.

## Public-repository rules

- Do not commit API tokens, OAuth client secrets, personal access tokens, passwords, private keys, or production webhook secrets.
- Treat n8n credential IDs, account labels, cached resource IDs, Airtable base/table IDs, chat/group destinations, private document URLs, and instance identifiers as environment-specific data that should be replaced before reuse.
- Use synthetic lead data for public testing.
- Keep the workflow inactive until all credentials and resource identifiers are replaced in a controlled environment.
- Rotate any secret if there is evidence that it was accidentally committed or shared publicly.

## Current evidence boundary

The repository demonstrates architecture and implementation patterns. It is not a security certification, penetration-test result, or proof of production hardening.

Report sensitive security concerns privately to the repository owner rather than posting secrets in a public issue.
