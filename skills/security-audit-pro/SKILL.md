---
name: security-audit-pro
description: Professional adversarial security audit skill for coding agents. Use for security audits, vulnerability reviews, pen-tests, or security questions. Supports Quick, Standard and Deep profiles. Produces clear actionable reports with independent verification. Inspired by Cloudflare security-audit-skill.
---

# Security Audit Pro

A clearer, more usable, and professionally packaged upgrade of the adversarial security audit methodology.

**Goal:** Find real trust-boundary violations, validate them adversarially, and deliver clear actionable reports.

## Supporting Files (load when needed)

**Core**
- [DOMAINS.md](DOMAINS.md) — Domain guides
- [HUNTING-TEMPLATES.md](HUNTING-TEMPLATES.md) — Ready hunting prompts
- [VALIDATION.md](VALIDATION.md) — Validation & reporting rules
- [SEVERITY.md](SEVERITY.md) — Severity scoring
- [SCHEMA.md](SCHEMA.md) — findings.json schema
- [CHECKLIST.md](CHECKLIST.md) / [CHECKLIST.fa.md](CHECKLIST.fa.md) — Phase checklist
- [QUICK-REFERENCE.md](QUICK-REFERENCE.md) — One-page card

**Operational**
- [GUIDANCE.md](GUIDANCE.md) / [GUIDANCE.fa.md](GUIDANCE.fa.md)
- [RESUME.md](RESUME.md) — How to continue interrupted audits
- [FALSE-POSITIVES.md](FALSE-POSITIVES.md) — Common weak candidates to reject
- [SCOPED-AND-MINIMAL.md](SCOPED-AND-MINIMAL.md) — Scoped & minimal modes
- [INTEGRATIONS.md](INTEGRATIONS.md) — How to use with different agents

## Operating Modes

- **Guidance mode** (default): Answer questions, review specific findings, explain methodology. Do not run the full workflow or create report files.
- **Full audit mode**: Only when the user explicitly asks for a security audit, pen-test, full review, or report artifacts.

If ambiguous, ask one clarifying question first.

## Profiles

| Profile     | Best for                          | Depth              | Cost   |
|-------------|-----------------------------------|--------------------|--------|
| **Quick**   | Small projects, first look        | Fast focused pass  | Low    |
| **Standard**| Most real-world projects          | Balanced           | Medium |
| **Deep**    | High-stakes or large codebases    | Maximum rigor      | High   |

## Core Principles (Non-negotiable)

1. Only real boundary failures with concrete principal, control, and result.
2. Finder never confirms its own candidate.
3. Severity only on confirmed (see SEVERITY.md).
4. needs_validation requires an exact missing fact (no severity).
5. Defense-in-depth gap without reachable violation = hardening only.
6. Source-first. Do not guess external behavior.
7. Multiple runs improve coverage (see RESUME.md).

## Full Audit Workflow

1. **Reconnaissance** — Map architecture & trust boundaries. Create ledger.
2. **Hunting** — Use DOMAINS.md + HUNTING-TEMPLATES.md.
3. **Validation** — Fresh verifier for every candidate (VALIDATION.md).
4. **Structured Output** — findings.json according to SCHEMA.md.
5. **Independent Verification** — Re-check confirmed records.
6. **Reporting** — REPORT.md (executive + prioritized + actionable), FINDINGS-DETAIL.md, NEEDS-VALIDATION.md.

Use CHECKLIST.md throughout. For interrupted runs see RESUME.md.

## Lightweight Mode

When sandbox is incomplete: stay source-only, mark execution-dependent items as needs_validation, never invent evidence.

## Anti-Patterns

1. Checklist items as vulnerabilities
2. Defense-in-depth without reachable violation
3. Guessing external behavior
4. Finder confirming its own finding
5. Severity on needs_validation
6. Report before independent verification
7. Stopping mid-phase without declaring incomplete

## Attribution

Inspired by Cloudflare’s security-audit-skill.  
This Pro edition adds clearer profiles, practical templates, severity guidance, resume support, bilingual operational files, and higher usability while preserving strict adversarial verification.

Copyright © 2026 Beig (Beig-Rules)
