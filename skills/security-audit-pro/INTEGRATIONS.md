# Integration Guide (Security Audit Pro)

## Skills CLI

```bash
npx skills add https://github.com/Beig-Rules/security-audit-pro --skill security-audit-pro
```

## Cursor
- Install via Skills / Rules mechanism or point the agent at the `skills/security-audit-pro` folder.
- Then ask: `run a standard security audit on this repo`

## Claude Code / Codex / similar agents
- Add the skill directory to the agent’s skill path or project rules.
- Use clear natural language triggers: “security audit”, “full security review”, “deep pen-test style review”.

## Recommended first prompts

```
run a quick security audit
```

```
do a standard security audit and produce the full report
```

```
perform a deep security audit focusing on authentication and multi-tenancy
```

```
continue the previous security audit from the last output folder
```

## Optional: GitHub / SARIF oriented workflow

You can later convert `findings.json` confirmed items into SARIF for GitHub Code Scanning.  
This skill focuses on high-quality adversarial findings first; SARIF export is an optional downstream step.
