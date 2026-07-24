---
name: Look up a practitioner or organisation by identifier
description: Authenticate to the NHSD FHIR API and resolve a practitioner, practitioner role, or organisation by name or a real-world identifier (AHPRA, Medicare provider number, ABN).
api: NHSD FHIR API
source: collections/nhsd-developers-portal.postman_collection.json
operations:
  - "POST /iam/oauth/token"
  - "GET /Practitioner"
  - "GET /PractitionerRole"
  - "GET /Organization"
---

# Look up a practitioner or organisation by identifier

Resolve a specific provider in the National Health Services Directory (NHSD) using an authoritative identifier.

## Steps
1. **Get an access token.** `POST https://iam.int.nhsd.healthdirect.org.au/iam/oauth/token` with `x-api-key` header and `grant_type=client_credentials&client_id=<id>&client_secret=<secret>`; read `accessToken`.
2. **Find a practitioner by AHPRA number.** `GET {base}/Practitioner?identifier=http://hl7.org.au/id/ahpra-registration-number|<AHPRA>`. Or search by name: `GET {base}/Practitioner?name=<full name>`.
3. **Find a practitioner role by Medicare provider number.** `GET {base}/PractitionerRole?identifier=http://ns.electronichealth.net.au/id/medicare-provider-number|<number>`.
4. **Find an organisation by ABN.** `GET {base}/Organization?identifier=nhsd:/reference/common/organisationIdentifierType/abn|<ABN>`. Or by name (`?name=`), or child organisations (`?partof=<orgId>`).
5. **Fetch a known record directly** by NHSD id: `GET {base}/Practitioner/{id}` (or `/PractitionerRole/{id}`, `/Organization/{id}`, `/HealthcareService/{id}`).

Every request carries `x-api-key` + `Authorization: Bearer <accessToken>`.

## Rules
- Identifier searches use the FHIR `system|value` token form; the systems above are the ones documented in the official NHSD Postman collection.
- Handle `401` (re-auth), `403` (credentials / AU geo-restriction), `404` (no match) per `errors/healthdirect-problem-types.yml`.
- Read-only surface — no writes. Auth model in `authentication/healthdirect-authentication.yml`.
