# Security Audit Report — Quick Profile (Example)

**Profile:** Quick  
**Status:** Complete

## Executive Summary

Fast triage completed. 1 confirmed medium finding. 2 items need validation.

## Confirmed Findings

### Medium — Missing ownership check on resource update

Impact: Authenticated user can modify another user’s resource.  
Recommendation: Add explicit ownership check before update.

## Needs Validation

- Whether production API gateway enforces additional auth headers.
- Whether debug endpoints are disabled in production deployment.
