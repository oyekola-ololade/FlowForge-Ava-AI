# Changelog

## 2026-09-03 — Evidence and repository hardening

### Changed

- Normalized workflow filename from `flowforge-ava.json.json` to `flowforge-ava.json` without changing the workflow blob/content.
- Replaced the one-byte `workflow/README.md` with actual import, evidence, and sanitization guidance.
- Upgraded the main README to separate implemented evidence from production-readiness claims.
- Added HOT-lead, human-handoff, and error-path architecture documentation.
- Added a buyer-facing critical-path SVG.

### Added

- `LICENSE`
- `SECURITY.md`
- `docs/CRITICAL_PATHS.md`
- `docs/VERIFICATION.md`
- `critical-paths.svg`

### Security / release note

The current checked-in workflow still contains environment-specific resource and credential references. This update documents that risk but does **not** claim the workflow has completed a portable release-sanitization pass.

### Evidence boundary

No workflow-logic improvement, production deployment, client outcome, load-test result, or production-security claim is created by this documentation/repository-hardening release.
