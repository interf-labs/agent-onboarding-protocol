---
name: interf-preview
description: >
  Preview enterprise rollout against a company profile. Produces
  resolution timelines, identifies stakeholders, and surfaces risks.
  Use when you want to understand what rollout looks like at a specific enterprise.
---

# Preview Enterprise Rollout

Generate a rollout preview for a specific enterprise based on an `interf.yaml` onboarding contract.

## Before You Start

1. **Load the contract.** Read the project's `interf.yaml`. If none exists, run the `interf-draft` skill first.
2. **Load canonical types.** Read [canonical-dependencies/index.md](../protocol/canonical-dependencies/index.md) for dependency relationships, blockers, and sector patterns.

## Step 1: Build Enterprise Profile

Research the target enterprise:
- **Sector** — financial services, healthcare, retail, technology, etc.
- **Size** — Fortune 500, mid-market, growth stage
- **Known systems** — Salesforce, SAP, Okta, etc. (from public info, job postings, tech stack databases)
- **Regulatory environment** — HIPAA, PCI-DSS, SOX, GDPR, etc.

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

## Step 3: Build Resolution Timeline

1. Order requirements by dependency chain (what blocks what)
2. Identify the critical path (longest sequential chain)
3. Group parallel work streams
4. Flag high-risk items

## Step 4: Present the Preview

For each requirement:
- Resolution approach and steps
- Stakeholders involved
- Estimated complexity (low / medium / high)
- Risks and mitigations
- What it's blocked by

Summary:
- **Critical path** with ordered dependencies
- **Parallel work streams** that can run concurrently
- **Top risks** across the rollout
- **Key stakeholders** and their involvement
