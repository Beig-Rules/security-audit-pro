# Security Audit Report — Standard Profile (Example)

**Profile:** Standard  
**Status:** Complete

## Executive Summary

Balanced audit completed. 2 confirmed findings (1 high, 1 medium). 3 items need validation.

## Confirmed Findings

### High — Broken object-level authorization

Impact: User A can read and modify User B’s objects.  
Evidence: Handler accepts object ID without ownership check.  
Recommendation: Centralize authorization helper and apply at every mutating route.

### Medium — Sensitive data in error responses

Impact: Internal identifiers and fragments of user data leak in errors.  
Recommendation: Return generic client errors; log details server-side only.

## Needs Validation

- Reverse-proxy header stripping behavior.
- IdP session binding configuration.
- Key rotation policy in deployment.
