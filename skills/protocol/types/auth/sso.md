---
id: auth.sso.saml
name: SSO via SAML
category: auth
systems: [okta, azure-ad, ping-identity, onelogin, google-workspace]
requires: []
blocked_by: [process.security-review]
related: [auth.sso.oidc, auth.api-credentials]
sectors: [all]
---

# SSO via SAML

Enterprise SSO integration using SAML 2.0 protocol. Vendor's application authenticates users through the enterprise identity provider.

## Template

- **what:** SSO endpoint for our service to authenticate your users
- **ready:** A test user can log into our app via your SSO and see their data

## Matches

Use this type when vendor says: "SSO integration", "SAML authentication", "single sign-on", "identity provider", "federated login"

---

# SSO via OIDC

`auth.sso.oidc`

Same as SAML but using OpenID Connect protocol. More common with modern/cloud-native enterprises.

## Template

- **what:** OIDC endpoint for our service to authenticate your users
- **ready:** A test user can complete the OIDC flow and access our application
