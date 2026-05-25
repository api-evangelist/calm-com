# Calm

Calm is an American digital wellness company headquartered in San Francisco that builds a mobile and web app focused on mindfulness, meditation, sleep, and mental health. Founded in 2012 by Michael Acton Smith and Alex Tew, Calm pairs a consumer freemium subscription app with two B2B products — Calm Business for employer-paid wellness benefits, and Calm Health for clinical mental health programs sold to health plans and large self-insured employers. Both B2B products integrate through a small Partner API surface, SAML 2.0 SSO, and SFTP-delivered eligibility files.

This repository is an API Evangelist profile of Calm's developer-facing surface.

## APIs

### Calm Partner API

A small OAuth 2.0 client-credentials REST API used by Calm Business and Calm Health partners to provision and revoke Calm subscriptions for partner end users. Three operations cover the subscription lifecycle:

- `POST /v0/authorize` — exchange `client_id` / `client_secret` for a short-lived JWT.
- `POST /v0/b2b/users/link` — link a partner user to a Calm subscription and receive a redirect URL.
- `DELETE /v0/b2b/users/{partner_user_id}` — cancel a partner user subscription.

Production is served from `https://auth.calm.com`; development from `https://auth-ga.aws-dev.useast1.calm.com`. Credentials are issued by Calm's B2B Engineering Team.

- Docs: <https://partner.calm.com/docs/api>
- OpenAPI: [openapi/calm-partner-api-openapi.yml](openapi/calm-partner-api-openapi.yml)
- JSON Schema: [json-schema/calm-partner-user-schema.json](json-schema/calm-partner-user-schema.json), [json-schema/calm-eligibility-file-schema.json](json-schema/calm-eligibility-file-schema.json)
- JSON-LD: [json-ld/calm-com-context.jsonld](json-ld/calm-com-context.jsonld)
- Capability: [capabilities/partner-subscriptions.yaml](capabilities/partner-subscriptions.yaml)
- Examples: [examples/](examples/)
- Vocabulary: [vocabulary/calm-com-vocabulary.yml](vocabulary/calm-com-vocabulary.yml)

### Partner SSO and Eligibility Files

Two non-REST integration surfaces sit alongside the Partner API.

- **Partner SSO** — SAML 2.0 IdP-initiated flow. Partners send IdP issuer, SSO URL, and signature cert; Calm returns `metadata.xml`. A unique `SubjectNameId` is required per partner user. Azure, Okta, Shibboleth, and Microsoft ADFS are supported. <https://partner.calm.com/docs/sso>
- **SFTP Eligibility Files** — CSV uploads to `sftp.ws.calm.com:22` at `/inbound/eligibility/` using OpenSSH key auth. Minimum one identifier column; up to three optional segmentation columns. Calm recommends monthly cadence. <https://partner.calm.com/docs/sftp-instructions>

## Products

- **Calm** — consumer app (iOS / Android / web / Apple Watch / Apple TV / Alexa) for meditation, sleep, mindfulness, and music.
- **Calm Business** — employer-paid Calm benefit for employee wellness. <https://business.calm.com>
- **Calm Health** — clinical mental health programs for health plans and self-insured employers. <https://health.calm.com>

## Open Source

Calm publishes a handful of utilities under [github.com/calm](https://github.com/calm), primarily iOS audio/video helpers (PersistentStreamPlayer, KenBurns, TSHAlphaVideos) and React-Intl ESLint plugins. There is no public consumer-facing developer SDK or OpenAPI spec for the consumer Calm app.

## Maintainer

Kin Lane — <kin@apievangelist.com>
