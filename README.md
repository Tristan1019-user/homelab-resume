# Homelab Security Portfolio

Static portfolio for Tristan Stiller's infrastructure, networking, and security engineering lab.

## Highlights

- Proxmox homelab with SR-IOV networking, native IPv6, VLAN segmentation, and default-deny firewalling
- Wazuh + Cowrie + CrowdSec + OPNsense SOAR pipeline
- Public AI-enriched threat intelligence feed: <https://threat-intel.101904.xyz>
- Local AI automation and voice-control systems

## Local Preview

Open `index.html` directly in a browser, or serve it locally:

```bash
python3 -m http.server 8000
```

Then visit <http://127.0.0.1:8000>.

## Deployment

This repo is designed to publish from `main` via GitHub Pages using the repository root as the static site source.
