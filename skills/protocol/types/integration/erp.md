---
id: integration.erp.api
name: ERP System Access
category: integration
systems: [sap, oracle-erp, netsuite, workday-financials, dynamics-365-fo]
requires: [auth.api-credentials, stakeholder.technical-lead]
blocked_by: [process.security-review, process.architecture-review]
related: [integration.erp.rfc, data.field-mapping]
sectors: [manufacturing, retail, financial-services]
---

# ERP System Access

Vendor needs to connect to the enterprise ERP for operational data — orders, inventory, financials, supply chain.

## Template

- **what:** API access to your ERP system (orders and inventory data)
- **ready:** We can query order records and inventory levels via API from our staging environment

## Matches

Use this type when vendor says: "ERP access", "SAP integration", "order data", "inventory system", "supply chain data", "financial records"

---

# ERP via SAP RFC

`integration.erp.rfc`

Direct SAP RFC/BAPI calls. More complex than REST API — requires SAP-specific connectivity.

## Template

- **what:** SAP RFC connectivity for real-time transaction processing
- **ready:** We can execute a test BAPI call and receive response data

---

# HRIS Access

`integration.hris.api`

Employee and organizational data from HR information system.

## Template

- **what:** Read access to your HRIS (employee profiles and org structure)
- **ready:** We can query the employee directory and retrieve org chart data via API
