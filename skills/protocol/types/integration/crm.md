---
id: integration.crm.api
name: CRM API Access
category: integration
systems: [salesforce, hubspot, dynamics-365, zoho, pipedrive, oracle-cx]
requires: [auth.api-credentials]
blocked_by: [process.security-review]
related: [integration.crm.bulk-export, data.field-mapping, stakeholder.data-team]
sectors: [all]
---

# CRM API Access

Read/write access to enterprise CRM system via API. One of the most common dependencies — almost any customer-facing automation needs CRM access.

## Template

- **what:** Read/write access to your CRM (contacts and opportunities)
- **ready:** We can create a contact and read an opportunity via API from our staging environment

## Matches

Use this type when vendor says: "access to your CRM", "read/write contacts", "opportunity data", "customer records", "Salesforce/HubSpot access"

---

# CRM Bulk Export

`integration.crm.bulk-export`

One-time or periodic bulk export of CRM data. Different from API access — this is batch data transfer for training models or backfilling.

## Template

- **what:** Bulk export of CRM records (contacts and opportunities, 12+ months)
- **ready:** We receive a data export of 12+ months of records in CSV or via bulk API
