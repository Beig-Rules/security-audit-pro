# Validation & Reporting Guide (Security Audit Pro)

## Phase 3 — Candidate Validation Rules

For every candidate the verifier must answer:

1. Is there a clear lower-trust principal?
2. Is there a concrete accepted input or action?
3. Is there an intended security control that should have stopped it?
4. Does the path actually cross that control?
5. Is there a meaningful observable result (unauthorized action, data exposure, etc.)?

### Outcomes

- **confirmed** — All five points are established with source evidence (and bounded local proof when needed).
- **needs_validation** — The hypothesis is solid but one exact fact outside pure source analysis is missing. State that fact clearly.
- **rejected** — Source evidence, visible controls, or lack of real impact disproves the candidate.

### Hard rules

- The original finder never validates its own candidate.
- Do not assign severity to `needs_validation`.
- Do not promote a candidate just because it “looks bad”.
- Prefer fewer high-quality confirmed findings.

## Phase 5 — Independent Record Verification

Before writing final reports:

- Re-check every `confirmed` record with a fresh perspective.
- Verify the source locations still match the claim.
- If a material detail changes, re-validate.

## Phase 6 — Report Quality Checklist

### REPORT.md must contain:

1. Short executive summary (overall risk picture + counts)
2. Prioritized list of confirmed findings
3. For each confirmed finding:
   - Clear title and severity
   - Short impact description
   - Evidence location (file / function)
   - Concrete recommendation
4. Brief note on remaining `needs_validation` items

### NEEDS-VALIDATION.md must contain:

- Each item with the **exact missing fact** the owner must check
- No severity scores
- No vague language

### General style

- Be precise and concise
- Avoid checklist noise
- Make every confirmed finding actionable
