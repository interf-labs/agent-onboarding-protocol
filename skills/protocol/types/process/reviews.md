---
id: process.security-review
name: Security Review
category: process
systems: []
requires: [stakeholder.security-team]
blocked_by: []
related: [process.compliance-review, process.architecture-review]
sectors: [all]
---

# Security Review

Enterprise's formal security assessment of the vendor. Typically includes security questionnaire, architecture review, and may require SOC2/ISO27001 evidence. One of the longest lead-time dependencies at Fortune 500 companies.

## Template

- **what:** Security review and approval for our integration
- **ready:** Security review completed and vendor approved for production integration

## Matches

Use this type when vendor says: "security review", "security assessment", "vendor risk assessment", "security questionnaire", "SIG/CAIQ"

---

# Compliance Review

`process.compliance-review`

Enterprise compliance team assesses whether the vendor meets regulatory requirements — HIPAA, GDPR, PCI-DSS, SOX.

## Template

- **what:** Compliance review for applicable regulatory frameworks
- **ready:** Compliance review completed and approved

---

# Architecture Review

`process.architecture-review`

Enterprise architecture review board evaluates technical design and alignment with enterprise standards.

## Template

- **what:** Architecture review of our integration design
- **ready:** Architecture review board has approved the integration pattern
