---
name: agent-onboarding-protocol
description: >
  The Agent Onboarding Protocol specification — the open standard
  format for declaring what vendors need from enterprise environments.
  Includes canonical dependency types for deterministic matching.
  Loaded automatically by interf-contract and interf-preview.
user-invocable: false
---

# Agent Onboarding Protocol

An open standard for declaring what vendors need from enterprise environments before rollout.

## Contract Format

See [spec.md](./spec.md) for the `interf.yaml` schema:
- `requirements` — what you need, with `what` + `ready` acceptance criteria
- `optional` — nice-to-have dependencies
- `canonical` — optional reference to a canonical dependency type

## Examples

See [examples.md](./examples.md) for realistic contracts across different rollout types.

## Canonical Dependency Types

See [canonical-dependencies/index.md](./canonical-dependencies/index.md) for the full reference.

**Always load these before declaring or previewing a contract.** Each type has:
- `id` — the canonical identifier (e.g. `integration.crm.api`)
- `template` — pre-written `what` + `ready` pair
- `matches` — phrases for mapping plain English
- `requires` / `blocked_by` / `related` — dependency relationships
- `systems` — known enterprise systems
- `sectors` — sector-specific considerations

| Category | Types | Reference |
|---|---|---|
| integration | CRM, ERP, HRIS, webhooks, email, ticketing | [integration/](./canonical-dependencies/integration/overview.md) |
| auth | SSO (SAML/OIDC), API credentials, service accounts | [auth/](./canonical-dependencies/auth/overview.md) |
| data | Field mapping, sample data, historical exports | [data/](./canonical-dependencies/data/overview.md) |
| infrastructure | Test environments, network access | [infrastructure/](./canonical-dependencies/infrastructure/overview.md) |
| stakeholder | Data team, security, IT, business owner, sponsor | [stakeholder/](./canonical-dependencies/stakeholder/overview.md) |
| process | Security review, compliance, training, procurement | [process/](./canonical-dependencies/process/overview.md) |

## How It Works

1. **Declare** — Vendor declares `interf.yaml` with every enterprise dependency.
2. **Deliver** — Contract is published to the Interf registry or sent directly to enterprise.
3. **Resolve** — Enterprise works through each requirement, audited against the `ready` criteria.
4. **Verify** — All requirements resolved. Rollout can proceed.
