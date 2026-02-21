# Sanitized Configuration Examples

Real configurations from a production homelab environment.
IPs, credentials, API keys, and domain-specific values have been replaced with placeholders.

> **Note:** This lab is under active development. These configs represent a working snapshot
> but may not reflect the latest state. The architecture and tooling evolve as new
> services are added and existing ones are hardened.

| File | Description |
|------|-------------|
| `wazuh-rules/cowrie.xml` | 12 custom Wazuh SIEM rules for Cowrie SSH honeypot detection |
| `wazuh-rules/authentik-caddy.xml` | 13 custom rules for Authentik SSO + Caddy reverse proxy |
| `caddy/Caddyfile` | Full Caddy reverse proxy config with CrowdSec, Authentik SSO, and wildcard TLS |

## Architecture Context

These configs are part of a fully automated SOAR pipeline:

```
Attacker → Cowrie Honeypot → Wazuh SIEM (these rules) → N8N SOAR → CrowdSec + OPNsense pf
```

Caddy serves as the reverse proxy for 23+ services with:
- CrowdSec bouncer (HTTP-level IP blocking)
- Authentik forward auth (SSO for all internal services)
- ZeroSSL wildcard certificate via acme.sh + Cloudflare DNS challenge
