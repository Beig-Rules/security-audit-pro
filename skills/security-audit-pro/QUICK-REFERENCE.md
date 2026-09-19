# Quick Reference Card — Security Audit Pro

## Modes
- Guidance → answer questions, no full report files
- Full Audit → only when user clearly asks for audit / pen-test / report

## Profiles
- Quick → fast triage
- Standard → default for most projects
- Deep → high-stakes / large codebases

## Verdicts
- confirmed → real boundary failure + evidence (has severity)
- needs_validation → solid hypothesis + exact missing fact (no severity)
- rejected → disproved

## Non-negotiable rules
1. Finder never confirms its own candidate
2. Severity only on confirmed
3. No guessing external behavior
4. Defense-in-depth gap ≠ vulnerability
5. Prefer fewer high-quality findings

## Report order
1. Executive summary
2. Prioritized confirmed findings (actionable)
3. Needs validation list (exact facts)

## Key files
- DOMAINS.md
- HUNTING-TEMPLATES.md
- VALIDATION.md
- SEVERITY.md
- CHECKLIST.md
- RESUME.md
