# Hunting Templates (Security Audit Pro)

Use these focused prompts during Phase 2. Adapt them to the target.

---

## Web & Authentication

- Look for every place a resource ID or object reference is taken from the user and used without a clear ownership or permission check.
- Check state-changing endpoints for CSRF protection when ambient credentials (cookies/session) are used.
- Inspect token/JWT handling for missing expiration, algorithm confusion, or key confusion.
- Find authentication bypass paths (debug flags, fallback logic, missing middleware).

## AI / LLM Applications

- Trace user or external input into the prompt or tool arguments.
- Check whether model output is rendered as HTML/JS/Markdown without sanitization.
- Verify that privileged tools cannot be triggered solely by model output without re-validation.
- Look for cross-user memory or retrieval leakage.

## Client-Side

- Find flows where `location`, `postMessage`, `localStorage`, or URL fragments reach `innerHTML`, `eval`, or similar sinks.
- Check `postMessage` handlers for missing origin validation.
- Look for tokens stored insecurely and later used for sensitive actions.

## Supply Chain

- Inspect `package.json` / lockfiles / CI scripts for install-time or build-time remote code execution.
- Look for secrets committed in the repository or printed in build logs.
- Check auto-update or plugin loading paths for missing integrity verification.

## Multi-tenancy & Data Isolation

- For every read/write path, ask: “Can principal A reach principal B’s data?”
- Check background jobs, exports, search, and caches for missing tenant filters.

## Availability

- Find parsers, uploads, or queries that accept unbounded input.
- Look for algorithms that become super-linear with attacker-controlled size.

---

**Always record candidates with a clear fingerprint and source location.**
