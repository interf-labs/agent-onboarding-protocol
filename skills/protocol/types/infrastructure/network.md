---
id: infra.network-access
name: Network Access
category: infrastructure
systems: []
requires: [stakeholder.it-admin, process.security-review]
blocked_by: []
related: [auth.api-credentials]
sectors: [all]
---

# Network Access

Vendor needs network-level access — firewall rules, IP allowlisting, VPN, or private connectivity.

## Template

- **what:** Network access from our cloud to your environment (IP allowlisting or VPN)
- **ready:** Our service can establish a connection to your endpoint from our production IPs

## Matches

Use this type when vendor says: "firewall rules", "IP allowlist", "VPN access", "network connectivity", "private link"
