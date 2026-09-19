# findings.json Schema (Security Audit Pro)

Simple, practical schema for machine-readable results.

```json
{
  "version": "1.0",
  "target": "repository-name-or-path",
  "profile": "quick | standard | deep",
  "run_status": "complete | incomplete",
  "incomplete_reason": "string (only if incomplete)",
  "generated_at": "ISO-8601 timestamp",
  "summary": {
    "confirmed": 0,
    "needs_validation": 0,
    "rejected": 0
  },
  "findings": [
    {
      "id": "unique-fingerprint",
      "verdict": "confirmed | needs_validation | rejected",
      "title": "Short clear title",
      "severity": "high | medium | low | null",
      "description": "What happens and why it matters",
      "impact": "Concrete impact statement",
      "evidence": {
        "files": ["path/to/file.ts"],
        "notes": "Key source observations"
      },
      "recommendation": "Concrete fix suggestion",
      "missing_fact": "Exact fact needed (only for needs_validation)",
      "domain": "web-auth | ai-llm | client-side | supply-chain | multi-tenancy | availability | other"
    }
  ]
}
```

### Rules

- `severity` must be `null` when verdict is `needs_validation` or `rejected`.
- `missing_fact` is required only for `needs_validation`.
- Prefer stable fingerprints so later runs can resume and deduplicate.
