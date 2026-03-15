---
id: integration.crm.api
system: salesforce
name: Salesforce CRM Access
---

# Salesforce CRM Access

Salesforce-specific considerations for CRM API integration.

## Setup Requirements

- Connected App created in Salesforce Setup
- OAuth 2.0 scopes: `api`, `refresh_token`
- IP allowlisting for vendor's production IPs
- Custom objects require Profile/Permission Set access

## Template

- **what:** Read/write access to your Salesforce instance (contacts and opportunities)
- **ready:** Our Connected App can authenticate via OAuth and CRUD a contact in your sandbox

## Common Gotchas

- Custom object field-level security may block access even with API permission
- Bulk API has separate daily limits from REST API
- Sandbox refresh cycles can break test integrations
