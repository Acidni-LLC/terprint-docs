# Terprint Documentation Site

Official documentation, support, and status pages for the Terprint cannabis data analytics platform.

## Sites Hosted

This repository serves multiple subdomains via Azure Static Web Apps:

| URL | Purpose | Path |
|-----|---------|------|
| `docs.terprint.com` | Documentation home | `/index.html` |
| `docs.terprint.com/doctor-portal` | Doctor Portal docs | `/doctor-portal/` |
| `docs.terprint.com/recommend` | AI Recommender API docs | `/recommend/` |
| `support.terprint.com` | Support & contact | `/support/` |
| `status.terprint.com` | System status | `/status/` |
| `terprint.com/privacy` | Privacy policy | `/privacy/` |

## Structure

```
terprint-docs/
├── index.html                 # Documentation home
├── doctor-portal/
│   └── index.html             # Doctor Portal documentation
├── recommend/
│   └── index.html             # AI Recommender API documentation
├── support/
│   └── index.html             # Support contact page
├── status/
│   └── index.html             # System status page
├── privacy/
│   └── index.html             # Privacy policy
├── staticwebapp.config.json   # Azure SWA routing config
└── .github/workflows/
    └── deploy.yml             # CI/CD pipeline
```

## Development

### Local Preview

Open any HTML file directly in a browser, or use a local server:

```bash
npx serve .
```

### Deployment

Deployment is automatic via GitHub Actions when pushing to `main`.

## DNS Configuration Required

The following DNS records need to be configured at IONOS:

| Type | Name | Target |
|------|------|--------|
| CNAME | `docs.terprint` | Azure SWA endpoint |
| CNAME | `support.terprint` | Azure SWA endpoint |
| CNAME | `status.terprint` | Azure SWA endpoint |
| TXT | `asuid.docs.terprint` | Azure verification token |
| TXT | `asuid.support.terprint` | Azure verification token |
| TXT | `asuid.status.terprint` | Azure verification token |

Additionally, `terprint.com/privacy` requires the apex domain to be configured.

## Version

v20260203-1

## License

Copyright © 2026 Acidni LLC. All rights reserved.
