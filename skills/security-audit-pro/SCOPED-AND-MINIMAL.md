# Scoped Audits & Minimal Mode (Security Audit Pro)

## Scoped Audit

You can limit the audit to:
- specific paths (`src/auth`, `packages/api`, …)
- one subsystem (authentication, payments, admin)
- one domain (e.g. only AI/LLM or only multi-tenancy)

Rules:
- Only create ledger units for in-scope surfaces.
- Mark everything else as out of scope (never as “covered”).
- Clearly state in the report that coverage is partial.

## Minimal Mode

For very small projects or extremely tight budgets:
- Use Quick profile
- Focus only on authentication, authorization, and obvious injection/XSS paths
- Still obey all confirmation rules (no lowering of evidence bar)
- Produce a short REPORT.md
