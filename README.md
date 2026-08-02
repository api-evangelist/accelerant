# Accelerant

APIs.json profile for **Accelerant Holdings (NYSE: ARX)** — the Accelerant Risk Exchange, a data-driven
marketplace connecting underwriters of specialty insurance risk (MGAs, program administrators, captive
managers, retail brokers) with risk capital providers.

- Website: https://accelerant.ai/
- Platform: https://app.accelerant.ai/
- Developer documentation: https://docs.accelerant.ai/ (Member authentication required)
- API host: https://api.accelerant.ai

## Profiling notes

Accelerant's API surface is Member-gated. As of the 2026-08-02 enrichment pass no OpenAPI, GraphQL,
AsyncAPI, MCP or A2A contract is retrievable anonymously — `api.accelerant.ai` is WAF-protected (403)
and `docs.accelerant.ai` redirects unauthenticated requests to platform sign-in. The full contract
discovery probe log is recorded in `well-known/accelerant-well-known.yml` under `x-contract-discovery`.

What Accelerant does publish anonymously, and what is captured here:

- `well-known/` — OpenID Connect discovery document and JWKS (saved verbatim), plus the probe index
- `authentication/` — the OIDC authentication profile derived from that discovery document
- `scopes/` — the OIDC scopes advertised by the platform
- `conformance/` — standards conformance, including ISO/IEC 27001:2022 certification
- `security/` — TLS/HSTS/DNS posture probe
- `packages/` — registry search result (no first-party SDKs published)
- `llms/` — generated llms.txt

Part of the [API Evangelist](https://apievangelist.com) network, published to [APIs.io](https://apis.io).
