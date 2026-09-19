# Additional Guidance for Agents

This file provides short, practical reminders when running under Security Audit Pro.

## When to stay in Guidance mode

- User asks “is this code vulnerable to X?”
- User asks how to fix a specific pattern
- User wants methodology explanation
- User has not clearly requested a full audit or report artifacts

## When to switch to Full audit mode

- User says “security audit this codebase”
- User asks for a full / comprehensive / end-to-end review
- User explicitly wants REPORT.md or findings files

## Profile selection hints

- No preference stated + small repo → suggest Quick
- No preference + normal application → suggest Standard
- User mentions “production”, “high stakes”, “thorough”, or large monorepo → suggest Deep

## Reporting quality checklist

Before finishing Phase 6, verify:

- [ ] REPORT.md starts with a short executive summary
- [ ] Confirmed findings are ordered by priority
- [ ] Every confirmed finding has a concrete recommendation
- [ ] needs_validation items each state the exact missing fact
- [ ] No severity is assigned to needs_validation
- [ ] Attribution / tool name is present if required by the run

## Lightweight mode reminder

If sandbox controls are incomplete:

- Do not invent execution results
- Move any execution-dependent claim to needs_validation
- Still deliver maximum source-based value in the reports
