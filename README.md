# Agent Onboarding Protocol

An open standard for declaring what vendors need from enterprise environments before rollout.

## Install

```bash
npx skills add interf-labs/agent-onboarding-protocol
```

Then tell your coding agent:

```
draft an onboarding contract for this project and preview rollout for BlackRock
```

## Skills

| Skill | Purpose |
|---|---|
| `interf-draft` | Draft an `interf.yaml` onboarding contract |
| `interf-preview` | Preview enterprise rollout against a company profile |
| `agent-onboarding-protocol` | Protocol spec + canonical dependency types (loaded automatically) |

## The Contract

```yaml
name: crm-automation
version: 0.2.0
description: Automates CRM data entry and follow-up scheduling

requirements:
  - what: Read/write access to your CRM (contacts and opportunities)
    ready: We can create a contact and read an opportunity via API from staging
    canonical: integration.crm.api

  - what: SSO endpoint for our service to authenticate your users
    ready: A test user can log into our app via your SSO
    canonical: auth.sso.saml

  - what: Security review and approval for our integration
    ready: Security review completed and vendor approved
    canonical: process.security-review

optional:
  - what: Webhook endpoint for real-time updates
    ready: We receive a test webhook within 5 seconds of a CRM update
    canonical: integration.webhook.outbound
```

## Canonical Dependencies

31 canonical types across 6 categories. Each type has an ID, template, match phrases, and relationships.

| Category | Types | Covers |
|---|---|---|
| `integration.*` | 11 | CRM, ERP, HRIS, webhooks, email, ticketing |
| `auth.*` | 4 | SSO (SAML/OIDC), API credentials, service accounts |
| `data.*` | 3 | Field mapping, sample data, historical exports |
| `infra.*` | 2 | Test environments, network access |
| `stakeholder.*` | 5 | Data team, security, IT, business owner, sponsor |
| `process.*` | 6 | Security review, compliance, training, procurement |

Browse the full reference: [canonical-dependencies/](./canonical-dependencies/)

Each type can be expanded with:
- `systems/` — system-specific patterns (Salesforce, SAP, Okta...)
- `sectors/` — sector-specific patterns (healthcare, financial services...)
- `use-cases/` — real rollout scenarios

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md) for how to add new types, system-specific files, sector patterns, and use-cases.

## Related

| Repo | Purpose |
|---|---|
| [cli](https://github.com/interf-labs/cli) | CLI tooling — validate, publish, preview |
| [interf.com](https://interf.com) | Documentation |

## License

MIT — [Interf, Inc.](https://interf.com)
