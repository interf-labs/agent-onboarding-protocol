# Agent Onboarding Protocol

An open standard for declaring what vendors need from enterprise environments before rollout.

## Install

```bash
npx skills add interf-labs/agent-onboarding-protocol
```

## Skills

### `declare`

Declare an `interf.yaml` onboarding contract — scan your codebase and extract every enterprise dependency, or define them manually.

**Use when:**
- "Declare an onboarding contract for this project"
- "What do we need from enterprise to roll out?"
- "Create an interf.yaml"

### `preview`

Preview enterprise rollout against a company profile. Produces per-requirement analysis: resolution timelines, stakeholders, risks, blockers, and critical path to production.

**Use when:**
- "Preview rollout for BlackRock"
- "How long would it take to roll out at a Fortune 500 bank?"
- "What are the risks deploying at Goldman Sachs?"

### `protocol`

The protocol specification. Loaded automatically by `declare` and `preview` — you don't need to install this separately.

**Covers:**
- `interf.yaml` schema and field definitions
- Canonical dependency types (integration, auth, data, infrastructure, stakeholder, process)
- Example contracts across different industries

## The Onboarding Contract

The unit of work is an `interf.yaml` file. Each requirement is a `what` + `ready` pair — what you need from enterprise, and how they verify it's done:

```yaml
name: acme-crm-automation
version: 0.2.0
description: Automates CRM data entry and follow-up scheduling

requirements:
  - what: Read/write access to your CRM (contacts and opportunities)
    ready: We can create a contact and read an opportunity via API from our staging environment
    canonical: integration.crm.api

  - what: SSO endpoint for our service to authenticate your users
    ready: A test user can log into our app via your SSO and see their CRM data
    canonical: auth.sso.saml

  - what: Someone from your data team to map your custom fields to our schema (~4 hours)
    ready: Field mapping document completed and signed off by both sides
    canonical: stakeholder.data-team

  - what: Test environment with sample CRM data for validation
    ready: We can run our full test suite against the environment without errors
    canonical: infra.test-environment

optional:
  - what: Webhook endpoint for real-time update notifications
    ready: We receive a test webhook payload within 5 seconds of a CRM update
    canonical: integration.webhook.outbound
```

Plain English. Any stakeholder can read it. The `canonical` field maps each requirement to a known dependency type — added automatically by the declare skill, never required.

## Canonical Types

Each `canonical` field maps a requirement to a known dependency type. This enables deterministic matching — if enterprise has already resolved `auth.sso.saml` for one vendor, it auto-resolves for every other vendor that needs it.

| Category | Covers |
|---|---|
| `integration.*` | CRM, ERP, HRIS, email, webhooks, ticketing, analytics |
| `auth.*` | SSO (SAML/OIDC), API credentials, service accounts |
| `data.*` | Historical exports, field mapping, sample data |
| `infra.*` | Test environments, network/firewall, compute |
| `stakeholder.*` | Data team, security, IT admin, executive sponsor |
| `process.*` | Security review, legal/DPA, procurement, training |

See [skills/protocol/types/](./skills/protocol/types/) for the full reference with match patterns.

## How It Works

1. **Declare** — Your coding agent scans the codebase and declares every enterprise dependency in `interf.yaml`. Or you write it manually.
2. **Deliver** — Send the contract to enterprise. Via the Interf platform, email, or however you work today.
3. **Resolve** — Enterprise works through each requirement. The `ready` criteria tell them exactly when it's done.
4. **Verify** — All requirements resolved. Rollout can proceed.

## CLI

```bash
npx interf                # Install skills to your coding agent
npx interf validate       # Validate interf.yaml against the schema
npx interf publish        # Publish to the Interf registry (coming soon)
npx interf simulate       # Simulate rollout across profiles (coming soon)
```

## Contributing

The canonical dependency types grow over time. To add a new type:

1. Add entries to `skills/protocol/types/<category>/<detail>.md`
2. Update the category `overview.md`
3. Submit a PR describing what use-case it covers

## License

MIT — [Interf, Inc.](https://interf.com)
