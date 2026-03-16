# Agent Onboarding Protocol

An open standard for declaring what vendors need from enterprise environments before rollout.

## Install

```bash
npx skills add interf-labs/agent-onboarding-protocol
```

## Skills

### `interf-declare`

Declare an `interf.yaml` onboarding contract — scan your codebase and extract every enterprise dependency, or define them manually.

**Use when:**
- "Declare an onboarding contract for this project"
- "What do we need from enterprise to roll out?"

### `interf-preview`

Preview enterprise rollout against a company profile — resolution timelines, stakeholders, risks, and critical path.

**Use when:**
- "Preview rollout for BlackRock"
- "How long would it take to roll out at a Fortune 500 bank?"

### `agent-onboarding-protocol`

The protocol specification. Loaded automatically by the other skills.

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

optional:
  - what: Webhook endpoint for real-time updates
    ready: We receive a test webhook within 5 seconds of a CRM update
    canonical: integration.webhook.outbound
```

## Related Repositories

| Repo | Purpose |
|---|---|
| [canonical-dependencies](https://github.com/interf-labs/canonical-dependencies) | Canonical dependency types — the shared vocabulary |
| [cli](https://github.com/interf-labs/cli) | CLI tooling — validate, publish, simulate |
| [interf.com](https://interf.com) | Documentation and platform |

## License

MIT — [Interf, Inc.](https://interf.com)
