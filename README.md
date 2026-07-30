# Lena Health

Lena Health is a Houston, Texas healthcare technology company founded in the Texas Medical Center that combines AI agents with human care navigators to deliver care coordination at scale. Its LenaConnect platform handles routine patient outreach calls, appointment scheduling and coordination, payer and provider hold times, automatic call documentation, EHR integration, and resource and referral management.

Lena offers fully managed care navigation services covering Chronic Care Management (CCM), Transitional Care Management (TCM), rising-risk care management, and annual wellness visits, working with health plans, ACOs, health systems, provider groups, care management providers, and community organizations.

Backed by: techstars — https://lena.io/

## API surface

**No public API.** Enrichment found no developer portal, API documentation, OpenAPI/AsyncAPI specification, SDKs, or public API host. `api.lena.io`, `docs.lena.io`, `developer.lena.io`, `api.lenaconnect.com`, and `app.lenaconnect.com` do not resolve. The platform is delivered as a managed service, with EHR integration handled through customer engagements rather than a self-serve API.

Because there is no specification to ground them in, the spec-dependent artifacts (openapi, mcp, skills, overlays, errors, scopes, authentication, conventions, data-model, sandbox, cli, components, asyncapi, agentic-access) are intentionally absent rather than fabricated.

## Artifacts

| Artifact | File | Method |
|---|---|---|
| llms.txt | `llms/lena-health-llms.txt` | searched (verbatim from https://lena.io/llms.txt) |
| Well-known index | `well-known/lena-health-well-known.yml` | probed |
| robots.txt | `well-known/lena-health-robots.txt` | searched (verbatim) |
| sitemap.xml | `well-known/lena-health-sitemap.xml` | searched (verbatim) |
| Trust center | `security/lena-health-trust-center.yml` | searched |
| Domain security | `security/lena-health-domain-security.yml` | probed |
| Conformance | `conformance/lena-health-conformance.yml` | searched |

## Notes

- **Compliance:** HIPAA compliant and SOC 2 Type II certified; trust center at https://trust.lenaconnect.com/ (hosted off the marketing domain, client-side rendered).
- **SPA soft-404 trap:** `lena.io` returns its 8,057-byte `index.html` with HTTP 200 for every unresolved path. Automated probes of `/.well-known/*` and `/trust` therefore appear to succeed but return HTML. Treat any 200 from this host as unverified until the body is inspected.
- **No vulnerability disclosure program** was found — no `security.txt`, disclosure page, or bug bounty — so no `Security` pointer is wired.
- **AI-crawler policy:** `robots.txt` allows all crawlers site-wide and blocks roughly 25 named AI/search agents (GPTBot, ClaudeBot, PerplexityBot, Google-Extended, CCBot, …) from a single obscure path, `/notice-7f3a2b9c`.
- **Domain security:** TLS 1.3 with HSTS (max-age 63072000), but no DNSSEC, no CAA records, no SPF, and DMARC at `p=none`.
