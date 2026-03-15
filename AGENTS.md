# Agent Onboarding Protocol

This repository contains the Agent Onboarding Protocol — an open standard for declaring what vendors need from enterprise environments before rollout.

## Skills

Install all skills:

```bash
npx skills add interf-labs/agent-onboarding-protocol
```

| Skill | Purpose |
|---|---|
| `declare` | Declare an `interf.yaml` onboarding contract |
| `preview` | Preview enterprise rollout against a company profile |
| `protocol` | Protocol specification and canonical dependency types |

## Structure

- `skills/declare/SKILL.md` — Load this to declare an onboarding contract
- `skills/preview/SKILL.md` — Load this to preview a rollout
- `skills/protocol/` — Spec, examples, and canonical dependency types (loaded automatically by declare and preview)

## Contributing

To expand canonical dependency types, add entries to `skills/protocol/types/<category>/` and submit a PR.
