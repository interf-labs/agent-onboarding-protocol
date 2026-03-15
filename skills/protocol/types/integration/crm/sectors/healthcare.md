---
id: integration.crm.api
sector: healthcare
name: CRM Access in Healthcare
---

# CRM Access in Healthcare

Sector-specific considerations for CRM integration at hospitals, health systems, and healthcare enterprises.

## Additional Dependencies

- `process.compliance-review` — HIPAA BAA required before any data access
- `process.security-review` — PHI data handling review
- `stakeholder.security-team` — HIPAA security officer sign-off

## Common Constraints

- PHI (Protected Health Information) cannot leave the enterprise network without BAA
- De-identification required for any data used in non-production environments
- Access logs must be retained for 6 years (HIPAA requirement)

## Template Adjustment

- **what:** Read/write access to your CRM with HIPAA BAA in place
- **ready:** BAA signed, our service can access approved record types, and PHI handling audit confirms compliance
