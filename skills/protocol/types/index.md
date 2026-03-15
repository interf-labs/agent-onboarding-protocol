---
description: Canonical dependency types for the Agent Onboarding Protocol
---

# Canonical Types

Quick reference for mapping vendor requirements to canonical types.

| Category | Description | Types |
|---|---|---|
| [integration](./integration/overview.md) | CRM, ERP, HRIS, webhooks, email, ticketing | 11 types |
| [auth](./auth/overview.md) | SSO, API credentials, service accounts | 4 types |
| [data](./data/overview.md) | Field mapping, sample data, historical exports | 3 types |
| [infrastructure](./infrastructure/overview.md) | Test environments, network access | 2 types |
| [stakeholder](./stakeholder/overview.md) | Data team, security, IT, business owner, sponsor | 5 types |
| [process](./process/overview.md) | Security review, compliance, training, procurement | 6 types |

**Total: 31 canonical types across 6 categories.**

## How to use

1. Read the vendor's plain English requirement
2. Find the matching category above
3. Navigate to the type file for the `canonical` ID, template, and related types
4. If no match exists, leave `canonical` empty — the requirement works with plain English alone
