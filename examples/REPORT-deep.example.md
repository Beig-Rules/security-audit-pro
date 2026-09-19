# Security Audit Report — Deep Profile (Example)

**Profile:** Deep  
**Status:** Complete

## Executive Summary

Deep adversarial audit completed with independent re-verification.  
3 confirmed findings (1 high, 2 medium). 4 precise needs-validation items remain.

## Confirmed Findings

### High — Privilege escalation via role update path

Impact: Lower-privileged authenticated user can elevate their own role.  
Recommendation: Enforce role-change authorization at the last trusted decision point and add regression test.

### Medium — Cross-tenant data exposure in search index

Impact: Search results can include objects from other tenants under specific queries.  
Recommendation: Apply tenant filter at query construction time.

### Medium — LLM tool call trusts model output for sensitive action

Impact: Prompt injection can trigger privileged tool without re-validation.  
Recommendation: Re-validate all tool arguments against caller permissions before execution.

## Needs Validation

- Production network policy for internal admin ports.
- Exact model system-prompt protections in deployed environment.
- Whether backup export job runs under least-privilege identity.
- CDN cache key behavior for authenticated responses.
