---
name: enterprise-readiness-protocol
description: "Defines the interf.yaml schema for enterprise readiness contracts — validation rules, field specifications, and canonical dependency types. Provides spec.md for schema reference and examples.md for realistic contract templates. Loaded automatically by interf-draft and interf-preview when drafting or previewing enterprise rollout contracts."
user-invocable: false
---

# Enterprise Readiness Protocol

An open standard for declaring what vendors need from enterprise environments before rollout.

## Contract Format

Every contract is an `interf.yaml` file with `what` + `ready` pairs:

```yaml
name: acme-crm-automation
version: 0.1.0
description: Automates CRM data entry

requirements:
  - what: Read/write access to your CRM (contacts and opportunities)
    ready: We can create a contact and read an opportunity via API from staging
    canonical: integration.crm.api

optional:
  - what: Webhook endpoint for real-time CRM updates
    ready: We receive a test webhook payload within 5 seconds of a CRM update
    canonical: integration.webhook.outbound
```

See [spec.md](./spec.md) for the full schema and validation rules. See [examples.md](./examples.md) for realistic contracts across different rollout types.

## How It Works

1. **Draft** — Vendor creates `interf.yaml` listing every enterprise dependency with `what` + `ready` criteria. Run `npx interf validate` to check schema and canonical type IDs.
2. **Deliver** — Contract is published to the Interf registry or sent directly to enterprise.
3. **Resolve** — Enterprise works through each requirement, audited against the `ready` criteria.
4. **Verify** — All requirements resolved and acceptance criteria met. Rollout can proceed.
