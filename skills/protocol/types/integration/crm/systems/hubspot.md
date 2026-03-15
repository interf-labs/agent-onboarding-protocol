---
id: integration.crm.api
system: hubspot
name: HubSpot CRM Access
---

# HubSpot CRM Access

HubSpot-specific considerations for CRM API integration.

## Setup Requirements

- Private App created in HubSpot Settings
- Scopes granted per object type (contacts, deals, companies)
- Rate limits: 100 requests per 10 seconds (private app)

## Template

- **what:** Read/write access to your HubSpot CRM (contacts and deals)
- **ready:** Our private app can authenticate and CRUD a contact in your HubSpot instance

## Common Gotchas

- HubSpot API v3 vs v1 — ensure vendor specifies which version
- Association API needed for linking objects (contact → company)
- Custom properties require separate scope grants
