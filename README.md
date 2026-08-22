# Uplight (uplight)

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Uplight is a Boulder, Colorado energy technology company formed in 2019 from the merger of Tendril and Simple Energy and expanded through the acquisitions of EnergySavvy, FirstFuel, Ecotagious, EEme, and DERMS/VPP provider AutoGrid (closed February 2024). It sells software to electric and gas utilities and retailers in North America, Europe, and Asia rather than to consumers, covering energy efficiency and electrification marketplaces, home energy reports, rate engagement, demand response, distributed energy resource management (DERMS), virtual power plants, and a utility data lake with analytics. In the United States value chain Uplight sits on the utility side of the meter as a vendor and orchestration layer between the utility, its customers, and connected devices, and it publicly states support for OpenADR, IEEE 2030.5, Modbus, DNP3 and other SCADA protocols for DER control. Its API posture is honestly closed: a Developer Platform exists and is marketed to utilities and ecosystem partners, the documentation portal at docs.uplight.com serves a public landing shell but every Documentation and API Reference path redirects to a ReadMe login, and the production gateway at api.uplight.com answers anonymously only with HTTP 401 and a bearer-token error. No consumer usage-data API, no open market data, no downloadable OpenAPI, and no Green Button or ESPI reference could be found. Uplight is a software vendor, not a regulated data holder, so no consumer data mandate applies to it.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/uplight/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/uplight/refs/heads/main/apis.yml)

## Tags

- Energy
- United States
- Utilities
- Electricity
- Gas
- Demand Response
- DER
- Grid
- Virtual Power Plant
- DERMS
- Energy Efficiency
- Customer Engagement

## Timestamps

- **Created:** 2026-07-27
- **Modified:** 2026-07-27

## APIs

### Uplight Developer Platform API

Uplight markets a Developer Platform that exposes customer, program, eligibility, enrollment, device, and energy-flexibility data to utilities and ecosystem partners through APIs. The reference is published on a ReadMe portal at docs.uplight.com, but the `/developer` path 302-redirects to a ReadMe dashboard login, so no operation, schema, scope, or rate limit is publicly readable. The production gateway at api.uplight.com is real and reachable (Kong Enterprise 3.10) but returns HTTP 401 with `{"errors":[{"message":"Invalid or no token provided"}]}` to every anonymous request, including `/openapi.json`, `/swagger.json`, `/v1`, and `/.well-known/openid-configuration`.

- **Human URL:** [https://docs.uplight.com/](https://docs.uplight.com/)
- **Base URL:** `https://api.uplight.com`

#### Tags

- Energy
- Utilities
- Demand Response
- DER
- Customer Engagement

#### Properties

- [Documentation](https://docs.uplight.com/)
- [API Reference](https://docs.uplight.com/developer/reference) — gated, redirects to ReadMe login
- [Documentation](https://uplight.com/platform/)
- [Documentation](https://uplight.com/blog/uplights-developer-platform-decisions-made-easy-for-customers-and-utilities/)

## Mandate and Access Posture

| Dimension | Finding |
| --- | --- |
| Home market | United States |
| Mandate regime | `none` — a US software vendor, not a designated data holder; Green Button is voluntary in the US, and neither Ontario's Green Button regulation nor the Australian CDR reaches Uplight |
| Mandate status | `not-applicable` — no obligation attaches, and the standards Uplight does claim (OpenADR, IEEE 2030.5) are marketing claims with no conformance record found |
| Data standard | No Green Button / ESPI reference found. OpenADR, Modbus, DNP3, IEEE 2030.5 claimed for DER control — control protocols, not consumer data sharing. Public HTTP surface is proprietary. |
| Consumer data API | No — no documented public route for a third party to obtain an individual customer's usage or billing data |
| Open market data | No — no open grid, market, system, or emissions data published; `data.uplight.com` does not resolve |
| Access gate | `partner-only` — be a utility customer or contracted ecosystem partner and be issued portal credentials; no sign-up, no sandbox, no trial |
| Auth model | Bearer token behind Kong Enterprise 3.10; no OpenID Connect discovery document served anywhere |

Closed on both axes — no open market data and no documented consumer data API. Full probe log with HTTP status for every URL is in [review.yml](review.yml).

## Common Properties

- [Website](https://uplight.com/)
- [Documentation](https://docs.uplight.com/)
- [API Reference](https://docs.uplight.com/developer/reference)
- [About](https://uplight.com/about-us/)
- [Platform](https://uplight.com/platform/)
- [Partners](https://uplight.com/partners/)
- [Blog](https://uplight.com/blog/)
- [Blog RSS](https://uplight.com/blog/feed/)
- [Press](https://uplight.com/press/)
- [Privacy](https://uplight.com/privacy-policy/)
- [Terms of Service](https://uplight.com/terms-of-service/)
- [Cookie Policy](https://uplight.com/cookie-policy/)
- [Contact](https://uplight.com/contact-us/)
- [Resources](https://uplight.com/resources/)
- [Compliance](https://uplight.com/resources/integrated-approach-security-privacy-compliance/) — states independently-audited SOC 2 Type 2 reports
- [GitHub Organization](https://github.com/Uplight-Inc)
- [LinkedIn](https://www.linkedin.com/company/uplight)

## Artifacts

Uplight publishes no machine-readable contract, so most of the enrichment here is a
recorded negative — the probes and the absence are the finding.

| Artifact | Method | What it says |
|---|---|---|
| [conformance/uplight-conformance.yml](conformance/uplight-conformance.yml) | searched | OpenADR, IEEE 2030.5, Modbus, DNP3 recorded as **claimed, not verified**; no OpenAPI, no OIDC, no RFC 9457, no Green Button |
| [authentication/uplight-authentication.yml](authentication/uplight-authentication.yml) | probed | Bearer token at a Kong Enterprise 3.10 edge; grant type undeterminable anonymously; no discovery document; partner-only credential issuance |
| [lifecycle/uplight-lifecycle.yml](lifecycle/uplight-lifecycle.yml) | searched | No status page (`uplight.statuspage.io` is unclaimed), no public changelog, no versioning or deprecation policy, no published SLA |
| [security/uplight-compliance.yml](security/uplight-compliance.yml) | searched | SOC 2 Type 2 + third-party pen testing claimed on a public page; no trust center; no security.txt, no disclosure policy, no bug bounty |
| [security/uplight-domain-security.yml](security/uplight-domain-security.yml) | probed | TLS 1.3 on all three hosts, HSTS on the web hosts (not the gateway), SPF + DMARC `p=reject`, no DNSSEC, no CAA |
| [well-known/uplight-well-known.yml](well-known/uplight-well-known.yml) | searched | Every `/.well-known/` probe missed on every host; the ReadMe 200s are SPA shells, not documents |
| [llms/uplight-llms.txt](llms/uplight-llms.txt) | generated | Agent-facing summary that leads with "this API is gated — do not guess endpoints" |

No `openapi/`, `packages/`, `mcp/`, `skills/`, `sandbox/`, `changelog/`, or `errors/`
artifacts exist: there is no spec to derive from, no first-party SDK on any registry
(the three archived `Uplight-Inc` GitHub repos are internal tooling; `gbqschema-converter`
on PyPI is authored by an individual, not Uplight), and no public error or test surface.

## Maintainers

- Kin Lane — kin@apievangelist.com
