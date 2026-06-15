# Sift (sift-com)

Sift (formerly Sift Science) is the San Francisco-based Digital Trust and Safety platform that protects more than
700 global brands from payment fraud, account takeover, content abuse, promotion abuse, and money movement risk.
Sift's APIs ingest user, device, payment, content, and verification events, return real-time risk scores per
abuse type, automate decisions through Workflows, ship a Verification API for step-up challenges, and operate a
Console for analyst case management. Sift was founded in 2011, processes more than one trillion events per year,
and reports a median annual loss prevented of about $4.2M per customer.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/sift-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/sift-com/refs/heads/main/apis.yml)

## Scope

- **Position:** Consuming
- **Access:** 3rd-Party

## Tags

- Fraud Prevention
- Trust And Safety
- Risk Scoring
- Identity Verification
- Chargebacks
- Account Takeover
- Content Abuse

## Timestamps

- **Created:** 2025-09-15T00:00:00.000Z
- **Modified:** 2026-05-25

## APIs

### Sift Events API

The primary Sift integration surface. POST events such as `$create_account`, `$create_order`, `$transaction`,
`$login`, `$chargeback`, and `$verification` to api.sift.com/v205/events to feed Sift's fraud and abuse
models. Synchronous scoring and workflow status can be requested per call.

- **Human URL:** [https://developers.sift.com/docs/curl/events-api](https://developers.sift.com/docs/curl/events-api)

#### Tags

- Fraud
- Events
- Trust And Safety

#### Properties

- [Documentation](https://developers.sift.com/docs/curl/events-api)
- [OpenAPI](openapi/sift-events-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sift-events-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sift-events-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/sift-event-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/sift-create-order-example.json)

### Sift Decisions API

Apply and retrieve decisions (block, watch, accept) against Sift users, orders, sessions, and content.
Decisions feed Sift's ML models, drive downstream webhooks, and are the modern replacement for the legacy
Labels API.

- **Human URL:** [https://developers.sift.com/docs/curl/decisions-api](https://developers.sift.com/docs/curl/decisions-api)

#### Tags

- Decisions
- Fraud
- Workflows

#### Properties

- [Documentation](https://developers.sift.com/docs/curl/decisions-api)
- [OpenAPI](openapi/sift-decisions-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sift-decisions-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sift-decisions-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/sift-decision-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/sift-apply-decision-example.json)

### Sift Score API

Retrieve and recompute Sift Scores for a user across configured abuse types (payment, content, account
takeover, account abuse, promotion). Scores range from 0 to 100 and ship with reason codes that explain the
contributing model features.

- **Human URL:** [https://developers.sift.com/docs/curl/score-api](https://developers.sift.com/docs/curl/score-api)

#### Tags

- Scores
- Risk
- Fraud

#### Properties

- [Documentation](https://developers.sift.com/docs/curl/score-api)
- [OpenAPI](openapi/sift-score-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sift-score-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sift-score-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/sift-score-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Sift Verification API

Send, resend, and check user verification challenges across SMS, email, phone, push, biometric, and security
key channels. Outcomes are recorded on the user timeline and feed Sift's risk models.

- **Human URL:** [https://developers.sift.com/docs/curl/verification-api](https://developers.sift.com/docs/curl/verification-api)

#### Tags

- Verification
- MFA
- Identity

#### Properties

- [Documentation](https://developers.sift.com/docs/curl/verification-api)
- [OpenAPI](openapi/sift-verification-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sift-verification-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sift-verification-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/sift-verification-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Sift Workflows API

Sift Workflows automate decisions on users, orders, sessions, and content. The Workflows API surfaces
synchronous workflow status through the Events API (`return_workflow_status=true`) and exposes endpoints for
retrieving Workflow run history.

- **Human URL:** [https://developers.sift.com/docs/curl/workflows](https://developers.sift.com/docs/curl/workflows)

#### Tags

- Workflows
- Automation
- Fraud

#### Properties

- [Documentation](https://developers.sift.com/docs/curl/workflows)
- [OpenAPI](openapi/sift-workflows-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sift-workflows-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sift-workflows-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Sift Labels API

Apply and remove fraud labels on Sift users. Labels are training signal for Sift's risk models. Deprecated in
favor of the Decisions API for new integrations, but still supported for backfill.

- **Human URL:** [https://developers.sift.com/docs/curl/labels-api](https://developers.sift.com/docs/curl/labels-api)

#### Tags

- Labels
- Fraud
- Deprecated

#### Properties

- [Documentation](https://developers.sift.com/docs/curl/labels-api)
- [OpenAPI](openapi/sift-labels-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/sift-labels-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/sift-labels-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Portal](https://sift.com)
- [Documentation](https://developers.sift.com)
- [API Reference](https://developers.sift.com/docs/curl/api-overview)
- [Getting Started](https://developers.sift.com/tutorials)
- [Authentication](https://developers.sift.com/docs/curl/api-overview/authentication)
- [Rate Limits](https://developers.sift.com/docs/curl/api-overview/rate-limits)
- [Status Page](https://status.sift.com)
- [Changelog](https://status.sift.com/history)
- [Support](https://support.sift.com)
- [Blog](https://engineering.sift.com)
- [Blog](https://sift.com/blog)
- [Terms of Service](https://sift.com/legal-and-compliance)
- [Privacy Policy](https://sift.com/privacy-policy)
- [Console](https://console.sift.com)
- [Sign Up](https://console.sift.com/signup)
- [GitHub Organization](https://github.com/SiftScience)
- [SDK](https://github.com/SiftScience/sift-python)
- [SDK](https://github.com/SiftScience/sift-ruby)
- [SDK](https://github.com/SiftScience/sift-java)
- [SDK](https://github.com/SiftScience/sift-php)
- [SDK](https://github.com/SiftScience/sift-dotnet)
- [SDK](https://github.com/SiftScience/sift-ios)
- [SDK](https://github.com/SiftScience/sift-android)
- [SDK](https://github.com/SiftScience/sift-react-native)
- [LinkedIn](https://www.linkedin.com/company/siftscience)
- [Twitter](https://twitter.com/GetSift)
- [YouTube](https://www.youtube.com/c/SiftScience)
- [Spectral Rules](rules/sift-com-rules.yml)
- [Vocabulary](vocabulary/sift-com-vocabulary.yml)
- [JSON-LD](json-ld/sift-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Plans](plans/sift-com-plans-pricing.yml)
- [Rate Limits](rate-limits/sift-com-rate-limits.yml)
- [Fin Ops](finops/sift-com-finops.yml)
- [Features](undefined)
- [Use Cases](undefined)
- [Solutions](undefined)
- [Integrations](undefined)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
**URL:** https://apievangelist.com
