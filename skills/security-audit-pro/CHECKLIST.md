# Quick Operational Checklist (Security Audit Pro)

Use this as a lightweight control panel during a run.

## Before starting (Full audit mode)

- [ ] Profile chosen (Quick / Standard / Deep)
- [ ] Scope clarified (whole repo or specific paths/subsystems)
- [ ] Output directory agreed (if needed)
- [ ] Operating mode confirmed as Full audit

## Phase 1 — Reconnaissance

- [ ] Main entry points identified
- [ ] Authn / Authz surfaces mapped
- [ ] Trust boundaries listed
- [ ] Initial coverage ledger created

## Phase 2 — Hunting

- [ ] Relevant domains selected (see DOMAINS.md)
- [ ] Candidates recorded with clear fingerprints and source traces
- [ ] No candidate left as pure “smells bad”

## Phase 3 — Validation

- [ ] Every candidate given to a fresh verifier
- [ ] Verdict is one of: confirmed / needs_validation / rejected
- [ ] needs_validation items have an exact missing fact

## Phase 4 & 5

- [ ] findings.json written
- [ ] Independent verification of confirmed records done

## Phase 6 — Reporting

- [ ] REPORT.md starts with executive summary
- [ ] Confirmed findings are prioritized and actionable
- [ ] NEEDS-VALIDATION.md is precise
- [ ] No severity on needs_validation items
- [ ] Run marked complete (or incomplete with clear reason)

## Final quality gate

- [ ] Would a busy engineering manager understand the executive summary in 60 seconds?
- [ ] Can a developer act on each confirmed finding without guessing?
- [ ] Is every needs_validation item a real, specific question for the owner?
