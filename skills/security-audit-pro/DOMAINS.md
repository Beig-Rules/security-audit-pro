# Domain Guides (Security Audit Pro)

Use these short domain notes during hunting and validation.  
They are condensed, practical versions of the major attack surfaces.

---

## 1. Web Protocol & Authentication

**Look for:**
- Missing or bypassable authentication / authorization checks
- IDOR / broken object-level authorization
- CSRF on state-changing requests that rely on ambient credentials
- Session fixation, weak session handling, missing binding
- JWT / token issues (alg confusion, missing exp/nbf validation, key confusion)
- Open redirects that can be chained into auth flows
- Cache poisoning or request smuggling symptoms visible in source

**Confirmation rules:**
- Must show a concrete lower-trust principal reaching a higher-privilege action or data.
- If the decisive control lives only in a reverse proxy / IdP / gateway not present in the repo → `needs_validation`.

---

## 2. AI & LLM Applications

**Look for:**
- Prompt injection that reaches a privileged tool or action
- Insecure output handling (LLM output rendered as HTML/JS/Markdown without sanitization)
- Tool / function calling that trusts model output without re-validation
- Agent memory or retrieval that allows cross-user data leakage
- Over-privileged tools exposed to the model
- Missing human-in-the-loop on high-impact actions

**Confirmation rules:**
- Show attacker-controlled input → model → privileged side-effect or cross-principal disclosure.
- If the exact model, system prompt, or external tool behavior is not visible → `needs_validation`.

---

## 3. Client-Side / Browser

**Look for:**
- DOM XSS (location, postMessage, storage, URL fragments reaching dangerous sinks)
- postMessage without origin checks
- Prototype pollution that reaches a dangerous sink
- Insecure handling of tokens in localStorage / sessionStorage
- UI redress / clickjacking only when combined with a real sensitive action

**Confirmation rules:**
- Need a controllable source and a real executing or disclosing sink.
- Framework auto-escaping that actually protects the path can reject the candidate.

---

## 4. Supply Chain & Release

**Look for:**
- Unpinned or mutable dependencies that execute code at install/build time
- Scripts in package.json / CI that pull and run remote content
- Secrets in repositories or build logs
- Missing integrity checks (SRI, checksums, signature verification)
- Auto-update mechanisms without verification

**Confirmation rules:**
- Prefer findings that show actual code execution or secret exposure paths present in the repo.
- “Dependency is old” alone is not a confirmed vulnerability.

---

## 5. Data Isolation & Multi-tenancy

**Look for:**
- Missing tenant / owner checks on read or write paths
- Shared caches or search indexes that leak across tenants
- Export / backup / debug endpoints that ignore tenancy
- Background jobs that process data under the wrong identity

**Confirmation rules:**
- Demonstrate that principal A can read or modify principal B’s data through a reachable path.

---

## 6. Resource Exhaustion & Availability

**Look for:**
- Unbounded allocations or CPU work triggered by small attacker input
- Missing timeouts / size limits on parsers, uploads, or queries
- Algorithms with super-linear behavior reachable by untrusted input

**Confirmation rules:**
- Must show meaningful shared impact (not just “it can be slow for the attacker himself”).
- Pure theoretical complexity without a reachable trigger stays `needs_validation` or hardening.

---

## How to use these guides

- During Phase 2 (Hunting) pick the relevant domains for the target.
- During Phase 3 (Validation) apply the confirmation rules strictly.
- When in doubt, prefer `needs_validation` with a precise missing fact over a weak `confirmed`.
