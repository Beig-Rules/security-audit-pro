---
name: security-audit-pro
description: Professional adversarial security audit skill for coding agents. Use for security audits, vulnerability reviews, pen-tests, or security questions. Supports Quick, Standard and Deep profiles. Produces clear bilingual-friendly reports with independent verification. Inspired by Cloudflare security-audit-skill.
---

# Security Audit Pro

A clearer, more usable upgrade of the adversarial security audit methodology.

Find real trust-boundary violations. The agent that discovers a candidate never confirms it. Produce actionable reports.

## Operating Modes

- **Guidance mode** (default): Answer security questions, review specific findings, or give methodology advice. Do not automatically run the full six-phase workflow or create report files.
- **Full audit mode**: Run when the user explicitly asks for a security audit, pen-test, full/comprehensive review, or report artifacts. Then follow the structured workflow below.

If the request is ambiguous, ask one clear question before starting a full audit.

## Profiles

Choose or ask for one of these profiles:

- **Quick** — Fast first pass. Lower cost. Good for small projects or initial triage.
- **Standard** — Balanced coverage and rigor. Recommended for most projects.
- **Deep** — Maximum thoroughness and independent verification. Use for high-stakes or large codebases.

Profiles change breadth and redundancy. They never lower the evidence bar for a `confirmed` finding.

## Core Principles (Non-negotiable)

1. Only report real trust-boundary failures with a concrete affected principal/resource and observable result.
2. The finder never confirms its own candidate. A separate skeptical verifier must try to disprove it.
3. Severity is assigned only to `confirmed` findings (likelihood × impact).
4. `needs_validation` means a specific source-grounded hypothesis is blocked by a missing fact — it has no severity.
5. Defense-in-depth gaps without a reachable boundary violation are hardening notes, not vulnerabilities.
6. Prefer bounded local evidence. Do not guess deployment, proxy, IdP, or browser behavior that is not in the repository.

## High-level Workflow (Full Audit Mode)

1. **Reconnaissance** — Map architecture, trust boundaries, input surfaces, and build a coverage ledger.
2. **Coverage-led hunting** — Assign focused hunters according to the ledger and selected profile.
3. **Candidate validation** — Every unique candidate goes to a fresh verifier that tries to disprove it.
4. **Structured output** — Write `confirmed`, `needs_validation`, and `rejected` records. Validate against schema.
5. **Independent record verification** — Fresh agents verify final source claims.
6. **Reporting** — Produce clear `REPORT.md` (executive + prioritized), `FINDINGS-DETAIL.md`, and `NEEDS-VALIDATION.md`.

Stop only when reports are written and validators pass, or when the run is explicitly marked incomplete with a clear reason.

## Output Expectations

Always prefer clarity:

- Start `REPORT.md` with a short executive summary.
- List confirmed findings by priority.
- Make every confirmed finding actionable (what to change, where, and why).
- Keep `needs_validation` items precise about the exact missing fact.

## Lightweight / Degraded Mode

If a full OS-enforced sandbox is not available:

- Continue with source-only analysis.
- Mark any finding that would require execution as `needs_validation` with the exact missing capability.
- Never pretend execution happened when it did not.
- Still produce the report structure so the owner gets value.

## Attribution

Core methodology and rigorous design inspired by Cloudflare’s security-audit-skill.  
This Pro edition focuses on clearer profiles, better usability, bilingual documentation, and actionable reporting while preserving the adversarial verification standard.

Copyright © 2026 Beig (Beig-Rules)
