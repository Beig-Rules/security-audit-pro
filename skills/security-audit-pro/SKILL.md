---
name: security-audit-pro
description: Professional adversarial security audit skill for coding agents. Use for security audits, vulnerability reviews, pen-tests, or security questions. Supports Quick, Standard and Deep profiles. Produces clear actionable reports with independent verification. Inspired by Cloudflare security-audit-skill.
---

# Security Audit Pro

A clearer, more usable, and professionally packaged upgrade of the adversarial security audit methodology.

**Goal:** Find real trust-boundary violations, validate them adversarially, and deliver clear actionable reports.

## Supporting Files (load when needed)

- [DOMAINS.md](DOMAINS.md) — Practical domain guides (Web/Auth, AI/LLM, Client-Side, Supply Chain, Multi-tenancy, Availability)
- [VALIDATION.md](VALIDATION.md) — Detailed validation and reporting rules
- [CHECKLIST.md](CHECKLIST.md) — Operational checklist for every phase
- [GUIDANCE.md](GUIDANCE.md) — Short operational reminders

## Operating Modes

- **Guidance mode** (default)  
  Answer security questions, review specific findings, explain methodology, or investigate a single concern. Do **not** automatically run the full six-phase workflow or create report files.

- **Full audit mode**  
  Activate only when the user explicitly asks for a security audit, pen-test, full/comprehensive review, or report artifacts. Then follow the structured workflow below.

If the request could be either mode, ask one focused clarifying question before creating files or starting the complete workflow.

## Profiles

| Profile     | Best for                          | Depth              | Relative Cost |
|-------------|-----------------------------------|--------------------|---------------|
| **Quick**   | Small projects, first look, triage| Fast focused pass  | Low           |
| **Standard**| Most real-world projects          | Balanced coverage  | Medium        |
| **Deep**    | High-stakes or large codebases    | Maximum rigor      | High          |

Profiles change breadth and verification redundancy. They **never** lower the evidence bar for a `confirmed` finding.

## Core Principles (Non-negotiable)

1. **Only real boundary failures** — Name lower-trust principal, accepted input/action, intended control, crossed boundary, affected resource, and concrete result.
2. **Adversarial validation** — The finder never confirms its own candidate. A separate skeptical verifier must try to disprove it.
3. **Severity only on confirmed** — Likelihood × impact only for `confirmed` records.
4. **needs_validation is precise** — Exact missing fact required. No severity.
5. **Defense-in-depth ≠ vulnerability** — Missing extra layers without a reachable violation is hardening only.
6. **Source-first + bounded evidence** — Do not guess external/proxy/IdP/browser behavior absent from the repository.
7. **Multiple runs improve coverage** — Later runs build on prior ledgers.

## Full Audit Workflow (6 Phases)

1. **Reconnaissance** — Map architecture, trust boundaries, entry points, auth surfaces. Create coverage ledger.
2. **Coverage-led Hunting** — Use [DOMAINS.md](DOMAINS.md). Record candidates with clear source traces.
3. **Candidate Validation** — Fresh verifier for every candidate. Follow [VALIDATION.md](VALIDATION.md).
4. **Structured Output** — Write `findings.json` and update ledger.
5. **Independent Record Verification** — Re-verify confirmed records with fresh perspective.
6. **Reporting** — Produce `REPORT.md` (executive + prioritized + actionable), `FINDINGS-DETAIL.md`, `NEEDS-VALIDATION.md`.

Use [CHECKLIST.md](CHECKLIST.md) as the operational control panel throughout the run.

Stop only when reports are written or the run is explicitly marked incomplete with a clear reason.

## Verdict Definitions

- **confirmed** — Complete source trace + meaningful boundary-crossing result. Has severity.
- **needs_validation** — Solid hypothesis blocked by one exact missing fact. No severity.
- **rejected** — Disproved by source, visible controls, or lack of real impact.

## Lightweight / Degraded Mode

When full sandbox is unavailable:
- Continue with thorough source analysis.
- Mark execution-dependent claims as `needs_validation` with the exact missing capability.
- Never invent execution evidence.
- Still deliver maximum value through the report structure.

## Output Quality Rules

- `REPORT.md` starts with a short executive summary.
- Confirmed findings are prioritized and actionable.
- Every `needs_validation` item states the exact missing fact.
- Prefer fewer high-quality confirmed findings over many weak ones.

## Anti-Patterns (Never do these)

1. Checklist deviations presented as vulnerabilities.
2. Defense-in-depth gaps with no reachable boundary violation.
3. Guessing external behavior not present in source.
4. Finder confirming its own candidate.
5. Severity on `needs_validation`.
6. Writing the final report before independent verification.
7. Stopping mid-phase without declaring the run incomplete and explaining why.

## Attribution

Core adversarial methodology, independent verification principle, and rigorous evidence standards are inspired by Cloudflare’s security-audit-skill.

This Pro edition focuses on clearer profiles, higher usability, bilingual documentation, practical domain guides, actionable reporting, and graceful degradation while preserving the strict verification standard.

Copyright © 2026 Beig (Beig-Rules)
