---
name: agent-onboarding-protocol
description: >
  The Agent Onboarding Protocol specification — the open standard
  format for declaring what vendors need from enterprise environments.
  Loaded automatically by interf-declare and interf-preview.
user-invocable: false
---

# Agent Onboarding Protocol

An open standard for declaring what vendors need from enterprise environments before rollout. The onboarding contract makes enterprise dependencies explicit, previewable, and verifiable — so enterprises self-prepare and vendors stop waiting.

## Contract Format

See [spec.md](./spec.md) for the `interf.yaml` schema:
- `requirements` — what you need, with `what` + `ready` acceptance criteria
- `optional` — nice-to-have dependencies
- `canonical` — optional reference to a canonical dependency type

## Examples

See [examples.md](./examples.md) for realistic contracts across different rollout types.

## Canonical Dependency Types

The canonical types are maintained in a separate repository for independent versioning and community expansion:

**[interf-labs/canonical-dependencies](https://github.com/interf-labs/canonical-dependencies)**

When mapping a vendor requirement to a canonical type, fetch the latest reference from that repository. If no canonical type matches, leave the `canonical` field empty — the contract works with plain English alone.

## How It Works

1. **Declare** — Vendor declares `interf.yaml` with every enterprise dependency.
2. **Deliver** — Contract is published to the Interf registry or sent directly to enterprise.
3. **Resolve** — Enterprise works through each requirement, audited against the `ready` criteria.
4. **Verify** — All requirements resolved. Rollout can proceed.
