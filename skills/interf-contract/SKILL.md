---
name: interf-contract
description: >
  Create an interf.yaml onboarding contract by scanning the codebase for
  enterprise dependencies, or define them manually. Use when you need to
  specify what you need from enterprise before rollout.
---

# Declare Onboarding Contract

Extract or define an `interf.yaml` onboarding contract declaring what you need from enterprise environments.

## Before You Start

**Load the canonical dependency types first.** Read [the protocol skill's canonical-dependencies/index.md](../protocol/canonical-dependencies/index.md) to understand what canonical types are available. Use the correct canonical IDs — do not invent shorthand.

## Step 1: Analyze the Project

- What does this project do and who are the enterprise users?
- What external systems does it connect to?
- What data access is needed?
- What authentication/authorization is required?
- Who needs to be involved on the enterprise side?
- What reviews or approvals are typical?

Look at:
- Configuration files (environment variables, API endpoints, auth config)
- Integration code (API clients, database connections, webhook handlers)
- Documentation (architecture docs, setup guides, runbooks)
- Deployment config (infrastructure requirements, network rules)

## Step 2: Map to Canonical Types

For each dependency identified:

1. Read the [canonical-dependencies/](../protocol/canonical-dependencies/index.md) reference
2. Find the matching canonical type by description and match phrases
3. Use the canonical type's template as a starting point for `what` + `ready`
4. Customize the template to match the specific project's needs
5. If no canonical type matches, write the requirement in plain English and leave `canonical` empty

## Step 3: Write interf.yaml

```yaml
name: project-name
version: 0.1.0
description: What it does, one line

requirements:
  - what: Read/write access to your CRM (contacts and opportunities)
    ready: We can create a contact and read an opportunity via API from our staging environment
    canonical: integration.crm.api

  - what: SSO endpoint for our service to authenticate your users
    ready: A test user can log into our app via your SSO and see their CRM data
    canonical: auth.sso.saml

  - what: Security review and approval for our integration
    ready: Security review completed and vendor approved for production integration
    canonical: process.security-review

optional:
  - what: Webhook endpoint for real-time update notifications
    ready: We receive a test webhook payload within 5 seconds of a CRM update
    canonical: integration.webhook.outbound
```

## Rules

1. **Plain English first.** Every requirement must have `what` + `ready` in plain English. Canonical is a reference, not a replacement.
2. **Use correct canonical IDs.** Check the canonical-dependencies reference. Do not use shorthand like `sso` or `api-key` — use `auth.sso.saml` or `auth.api-credentials`.
3. **One dependency per item.** Don't combine "CRM access and SSO" into one requirement.
4. **`ready` must be verifiable.** Enterprise should be able to check the criteria without ambiguity.
5. **Include stakeholder dependencies.** If someone needs to be involved (data team, security team), that's a requirement too.
6. **Include process dependencies.** Security review, compliance review, training — these are the blockers FDEs hate discovering mid-flight.

## Step 4: Validate (Optional)

After writing `interf.yaml`, validate it against the protocol schema and canonical types:

```bash
npx interf validate
```

This checks:
- Schema correctness (name, version, requirements with `what` + `ready`)
- Canonical type IDs against the latest known types
- Suggests corrections for shorthand or hallucinated IDs (e.g. `sso` → `auth.sso.saml`)

If the CLI is not installed, suggest the user run `npx interf validate` — it auto-installs and validates in one step.
