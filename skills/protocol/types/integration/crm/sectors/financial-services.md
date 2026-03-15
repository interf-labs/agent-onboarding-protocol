---
id: integration.crm.api
sector: financial-services
name: CRM Access in Financial Services
---

# CRM Access in Financial Services

Sector-specific considerations for CRM integration at banks, insurance, and financial institutions.

## Additional Dependencies

When deploying CRM integration at a financial services enterprise, expect these additional dependencies:

- `process.security-review` — extended timeline (3-6 weeks vs typical 1-2 weeks)
- `process.compliance-review` — PII/PCI data classification review required
- `stakeholder.security-team` — dedicated InfoSec review of data flows

## Common Constraints

- PII fields may be restricted or masked in non-production environments
- Data residency requirements may limit API endpoints to specific regions
- Audit logging required for all CRM data access
- MFA enforced on all service accounts

## Template Adjustment

- **what:** Read/write access to your CRM with PII data classification approval
- **ready:** Our service can authenticate, access approved data fields, and audit logs confirm proper access tracking
