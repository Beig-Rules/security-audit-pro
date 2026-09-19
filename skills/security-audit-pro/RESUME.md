# Resume & Continue Support (Security Audit Pro)

Audits can be interrupted. This skill is designed to continue cleanly.

## How to resume

1. Keep the previous output directory (or at least `findings.json` + `coverage-ledger.json`).
2. Tell the agent:
   - “Continue the previous security audit from the last output folder”
   - or “Resume the standard audit and focus on remaining gaps”
3. The agent should:
   - Load prior confirmed / needs_validation / rejected records
   - Treat prior `needs_validation` and uncovered ledger units as priority work
   - Avoid re-reporting unchanged confirmed findings as new discoveries
   - Re-validate any finding whose source has changed

## Rules for resumed runs

- Same-source confirmed findings can be carried forward after a quick check.
- Changed source → must be re-validated.
- Prior `needs_validation` items become active work units again.
- Always declare whether the new run is complete or still incomplete.
