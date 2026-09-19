# Severity Scoring Guide (Security Audit Pro)

Severity is assigned **only** to `confirmed` findings.

Use **Likelihood × Impact**.

## Impact Levels

- **High Impact**: Unauthorized access to sensitive data, account takeover, privilege escalation, remote code execution, cross-tenant data access, or significant financial/operational damage.
- **Medium Impact**: Limited data exposure, bypass of non-critical controls, abuse of functionality that affects other users moderately.
- **Low Impact**: Minor information disclosure, low-value privilege misuse, or issues requiring complex preconditions with limited damage.

## Likelihood Levels

- **High Likelihood**: Easily reachable by a low-privilege or unauthenticated attacker with simple input.
- **Medium Likelihood**: Requires specific conditions, authenticated user, or moderate attacker knowledge.
- **Low Likelihood**: Needs rare preconditions, complex chaining, or high privileges already.

## Final Severity

| Likelihood → Impact | High Impact | Medium Impact | Low Impact |
|---------------------|-------------|---------------|------------|
| **High Likelihood** | High        | High / Medium | Medium     |
| **Medium Likelihood**| High / Medium | Medium      | Low        |
| **Low Likelihood**  | Medium      | Low           | Low        |

### Practical rules

- Prefer the higher severity when in doubt between two levels **only if** the impact is clearly demonstrated.
- Never inflate severity because a finding “feels serious”.
- If the impact is not clearly established, it should not be `confirmed` yet.
