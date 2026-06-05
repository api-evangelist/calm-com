# Calm (calm-com)

Calm is an American digital wellness company headquartered in San Francisco that builds a mobile and web app focused on mindfulness, meditation, sleep, and mental health. Founded in 2012 by Michael Acton Smith and Alex Tew, Calm offers guided meditations, Sleep Stories (long-form bedtime audio often narrated by celebrities), breathing exercises, mindfulness courses, music for focus and sleep, and a Daily Calm session. The consumer Calm app is distributed through the iOS App Store and Google Play under a freemium subscription model. The company also operates two B2B products. Calm Business sells the consumer experience to employers as an employee wellness benefit, and Calm Health is a clinical mental health offering for health plans and large self-insured employers, with structured programs aligned to clinical needs. Both B2B products are powered by the Calm Partner API (auth.calm.com/v0), a small OAuth 2.0 client-credentials REST surface that partner systems use to provision, link, and cancel Calm subscriptions for their members or employees. Partners also integrate via SAML 2.0 IdP-initiated SSO and SFTP-uploaded eligibility files (CSV at sftp.ws.calm.com:/inbound/eligibility/). Calm publishes a handful of open-source utilities under github.com/calm — primarily iOS audio/video helpers (PersistentStreamPlayer, KenBurns) and React-Intl ESLint plugins — but there is no public consumer-facing developer API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/calm-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/calm-com/refs/heads/main/apis.yml)

## Scope

- **Type:** Index
- **Position:** Provider
- **Access:** 3rd-Party

## Tags

- Mindfulness
- Meditation
- Sleep
- Mental Health
- Wellness
- Digital Health
- Mobile App
- Consumer
- Employee Wellness
- Digital Therapeutics
- B2B

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Calm Partner API

OAuth 2.0 client-credentials REST API used by Calm Business and Calm Health partners to provision and revoke Calm subscriptions for partner end users. Three operations cover the lifecycle - authorize the partner service, link a partner user, and cancel a partner user subscription. Credentials (client_id, client_secret) are issued by Calm's B2B Engineering Team and the API is served from auth.calm.com (production) and auth-ga.aws-dev.useast1.calm.com (development).

- **Human URL:** [https://partner.calm.com/docs/api](https://partner.calm.com/docs/api)

#### Tags

- Partner
- Subscriptions
- B2B
- Provisioning
- Authentication

#### Properties

- [Documentation](https://partner.calm.com/docs/api)
- [OpenAPI](openapi/calm-partner-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/calm-partner-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/calm-partner-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/calm-partner-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/calm-eligibility-file-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/calm-com-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Example](examples/calm-authorize-example.json)
- [Example](examples/calm-link-user-example.json)
- [Example](examples/calm-cancel-user-example.json)

## Common Properties

- [Website](https://www.calm.com)
- [Portal](https://www.calm.com)
- [Sign Up](https://www.calm.com/signup)
- [Pricing](https://www.calm.com/subscribe)
- [Documentation](https://partner.calm.com/docs/api)
- [Documentation](https://partner.calm.com/docs/sso)
- [Documentation](https://partner.calm.com/docs/sftp-instructions)
- [Product](https://business.calm.com)
- [Product](https://health.calm.com)
- [Product](https://app.calmhealth.com)
- [Support](https://support.calm.com)
- [Terms of Service](https://www.calm.com/terms)
- [Privacy Policy](https://www.calm.com/privacy)
- [Blog](https://blog.calm.com)
- [Press](https://www.calm.com/press)
- [Careers](https://www.calm.com/jobs)
- [Contact](https://support.calm.com/hc/en-us/requests/new)
- [App Store Apple](https://apps.apple.com/us/app/calm/id571800810)
- [App Store Google](https://play.google.com/store/apps/details?id=com.calm.android)
- [Twitter](https://twitter.com/calm)
- [LinkedIn](https://www.linkedin.com/company/calm-com)
- [Instagram](https://www.instagram.com/calm)
- [YouTube](https://www.youtube.com/c/calm)
- [Facebook](https://www.facebook.com/calm.com)
- [GitHub Organization](https://github.com/calm)
- [Features](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
