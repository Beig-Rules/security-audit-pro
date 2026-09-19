# Common False Positives (Security Audit Pro)

Reject or downgrade candidates that match these patterns unless strong evidence exists.

- “Dependency is outdated” with no demonstrated exploit path
- Missing secondary defense while a primary control already blocks the attack
- Generic “missing rate limiting” without shared impact
- Self-DoS only (attacker can only hurt their own session)
- Theoretical complexity issues with no reachable trigger
- Framework auto-escaping that actually protects the reported sink
- Issues that require already-compromised high privileges to exploit
- Deployment/proxy/IdP behavior that is not visible in the repository (use `needs_validation` instead of inventing it)
- Checklist items with no concrete boundary crossing

**Principle:** If you cannot name the lower-trust principal, the crossed control, and the concrete result, it is not a confirmed finding.
