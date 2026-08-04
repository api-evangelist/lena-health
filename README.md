# Lena Health

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
