---
name: security-audit-pro
description: Professional adversarial security audit skill for coding agents. Use for security audits, vulnerability reviews, pen-tests, or security questions. Supports Quick, Standard and Deep profiles. Produces clear actionable reports with independent verification. Inspired by Cloudflare security-audit-skill.
---

# Security Audit Pro

A clearer, more usable, and professionally packaged upgrade of the adversarial security audit methodology.

**Goal:** Find real trust-boundary violations, validate them adversarially, and deliver clear actionable reports.

## Operating Modes

- **Guidance mode** (default)  
  Answer security questions, review specific findings, explain methodology, or investigate a single concern. Do **not** automatically run the full six-phase workflow or create report files.

- **Full audit mode**  
  Activate only when the user explicitly asks for a security audit, pen-test, full/comprehensive review, or report artifacts. Then follow the structured workflow below.

If the request could be either mode, ask one focused clarifying question before creating files or starting the complete workflow.

## Profiles

Always prefer to use (or ask for) one of these profiles:

| Profile     | Best for                          | Depth              | Relative Cost |
|-------------|-----------------------------------|--------------------|---------------|
| **Quick**   | Small projects, first look, triage| Fast focused pass  | Low           |
| **Standard**| Most real-world projects          | Balanced coverage  | Medium        |
| **Deep**    | High-stakes or large codebases    | Maximum rigor      | High          |

Profiles change breadth, number of hunting waves, and verification redundancy.  
They **never** lower the evidence bar required for a `confirmed` finding.

## Core Principles (Non-negotiable)

1. **Only real boundary failures**  
   A finding must name the lower-trust principal, the accepted input/action, the intended control, the crossed boundary, the affected principal or resource, and a concrete observable result.

2. **Adversarial validation**  
   The agent that discovers a candidate never confirms it. A separate, skeptical verifier must actively try to disprove it.

3. **Severity only on confirmed**  
   Likelihood × impact is calculated only for `confirmed` records. `needs_validation` has no severity.

4. **needs_validation is precise**  
   It means a specific source-grounded hypothesis is blocked by an exact missing fact (deployment control, runtime behavior, external config, etc.).

5. **Defense-in-depth ≠ vulnerability**  
   Missing extra layers when a primary control already prevents the attack is a hardening note, not a finding.

6. **Source-first + bounded evidence**  
   Prefer static analysis + minimal local proof. Do not guess proxy, IdP, browser, or deployment behavior that is not visible in the repository.

7. **Multiple runs improve coverage**  
   Later runs should build on prior ledgers and focus on gaps.

## Full Audit Workflow (6 Phases)

Execute these phases in order when in Full audit mode:

### Phase 1 — Reconnaissance
- Map architecture, trust boundaries, entry points, authentication/authorization surfaces, and data flows.
- Identify major subsystems and deployment modes present in the repository.
- Create an initial `coverage-ledger.json` (what will be examined).
- Record any prior audit artifacts if they exist.

### Phase 2 — Coverage-led Hunting
- Assign focused hunting work according to the ledger and chosen profile.
- Hunters look for concrete candidates that violate a trust boundary.
- Record candidates with clear fingerprints and source traces.
- Use domain-specific knowledge (web, auth, AI/LLM, supply-chain, etc.) when relevant.

### Phase 3 — Candidate Validation
- Every unique candidate is given to a **fresh** verifier.
- The verifier’s job is to try to disprove the candidate.
- Outcomes: promote to `confirmed`, keep as `needs_validation` (with exact blocker), or `rejected`.

### Phase 4 — Structured Output
- Write all final records into `findings.json`.
- Validate structure and required fields.
- Update the coverage ledger.

### Phase 5 — Independent Record Verification
- Fresh agents re-verify the source claims of every retained `confirmed` and important `needs_validation` record.
- Material changes trigger another verification pass.

### Phase 6 — Reporting
Produce clear human-readable reports:

- `REPORT.md` — Start with a short executive summary, then prioritized confirmed findings with actionable recommendations.
- `FINDINGS-DETAIL.md` — Full technical details and evidence.
- `NEEDS-VALIDATION.md` — Precise list of items that need owner confirmation, each with the exact missing fact.

Stop only when the reports are written **or** the run is explicitly marked incomplete with a clear reason disclosed in the report.

## Verdict Definitions

- **confirmed**  
  Complete source trace + bounded observed (or safely demonstrable) result that crosses a trust boundary. Has severity.

- **needs_validation**  
  Source-grounded hypothesis blocked by one exact missing fact outside pure source analysis. No severity.

- **rejected**  
  Candidate was disproved by source evidence, visible controls, lack of meaningful impact, or impossible prerequisites.

## Lightweight / Degraded Mode

When a full OS-enforced sandbox is not available:

- Continue with thorough source-only analysis.
- Any finding that truly requires execution must be marked `needs_validation` with the exact missing capability.
- Never claim execution evidence that does not exist.
- Still produce the full report structure so the owner receives maximum value.

## Output Quality Rules

- Executive summary first in `REPORT.md`.
- Every confirmed finding must be actionable (what to change, roughly where, and why it matters).
- Keep language precise and avoid checklist-style noise.
- Prefer fewer high-quality confirmed findings over many weak ones.

## Anti-Patterns (Never do these)

1. Presenting checklist deviations as vulnerabilities.
2. Reporting defense-in-depth gaps with no reachable boundary violation.
3. Guessing external/proxy/IdP/browser behavior not present in source.
4. Letting the finding agent confirm its own candidate.
5. Assigning severity to `needs_validation`.
6. Writing the final report before independent verification.
7. Stopping mid-phase without marking the run incomplete and explaining why.

## Attribution

Core adversarial methodology, independent verification principle, coverage-ledger idea, and rigorous evidence standards are inspired by Cloudflare’s security-audit-skill.

This Pro edition focuses on clearer profiles, higher usability, bilingual documentation, actionable reporting, and graceful degradation while preserving the strict verification standard.

Copyright © 2026 Beig (Beig-Rules)
