---
name: interf-preview
description: "Preview enterprise rollout against a company profile — produces resolution timelines, identifies stakeholders, maps dependency chains, and surfaces risks. Use when generating a deployment plan, implementation preview, or go-to-market readiness assessment for a specific enterprise customer."
---

# Preview Enterprise Rollout

Generate a rollout preview for a specific enterprise based on an `interf.yaml` readiness contract.

## Before You Start

1. **Load the contract.** Read the project's `interf.yaml`. If none exists, run the `interf-draft` skill first.
2. **Load canonical types.** Read [canonical-dependencies/index.md](../protocol/canonical-dependencies/index.md) for dependency relationships, blockers, and sector patterns.
3. **Verify inputs.** Confirm the contract has at least one requirement with `what` + `ready` fields. If any `canonical` IDs are present, verify they resolve against the canonical-dependencies reference.

## Step 1: Build Enterprise Profile

Research the target enterprise:
- **Sector** — financial services, healthcare, retail, technology, etc.
- **Size** — Fortune 500, mid-market, growth stage
- **Known systems** — Salesforce, SAP, Okta, etc. (from public info, job postings, tech stack databases)
- **Regulatory environment** — HIPAA, PCI-DSS, SOX, GDPR, etc.

Verify the profile covers all four dimensions before proceeding — gaps here cascade into inaccurate timelines.

## Step 2: Analyze Each Requirement

For each requirement in the contract:

1. Load the canonical type definition (if `canonical` field exists)
2. Check for sector-specific files (e.g., `canonical-dependencies/integration/crm/sectors/financial-services.md`)
3. Check for system-specific files (e.g., `canonical-dependencies/integration/crm/systems/salesforce.md`)
4. Identify:
   - **Stakeholders** — who needs to be involved
   - **Dependencies** — what blocks this requirement (`blocked_by` field)
   - **Risks** — what could go wrong (from key risks / common gotchas)
   - **Complexity** — from the canonical type's complexity field

Flag any requirements where canonical types could not be resolved or where sector/system data is missing.

## Step 3: Build Resolution Timeline

1. Order requirements by dependency chain (what blocks what)
2. Identify the critical path (longest sequential chain)
3. Group parallel work streams
4. Flag high-risk items

Example dependency chain: `auth.sso.saml` → `integration.crm.api` → `data.historical-export` (SSO must be live before CRM API access, which must be live before historical data export can begin).

## Step 4: Present the Preview

For each requirement:

| Field | Description |
|-------|-------------|
| **Requirement** | The `what` from the contract |
| **Approach** | Resolution steps for this enterprise |
| **Stakeholders** | Who needs to be involved |
| **Complexity** | Low / Medium / High |
| **Risks** | What could go wrong and mitigations |
| **Blocked by** | Other requirements that must resolve first |

Summary:
- **Critical path** — ordered dependency chain with the longest sequential resolution time
- **Parallel work streams** — requirements that can be resolved concurrently
- **Top risks** — highest-impact risks across the rollout with mitigations
- **Key stakeholders** — all involved parties and their requirements
