# Uplight (uplight)

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
