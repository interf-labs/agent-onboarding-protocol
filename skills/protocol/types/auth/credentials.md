---
id: auth.api-credentials
name: API Credentials
category: auth
systems: []
requires: []
blocked_by: [process.security-review]
related: [auth.sso.saml]
sectors: [all]
---

# API Credentials

API keys, OAuth client credentials, or service account tokens that vendor's service uses to connect to enterprise systems.

## Template

- **what:** API credentials for our service to connect
- **ready:** Our service authenticates and completes a round-trip API call

## Matches

Use this type when vendor says: "API key", "OAuth credentials", "service account", "client ID and secret", "bearer token"

---

# Service Account

`auth.service-account`

Dedicated service identity (not tied to a human user) for vendor's automated processes.

## Template

- **what:** Service account with appropriate permissions for our automated workflows
- **ready:** Our service can authenticate as the service account and perform all required operations
