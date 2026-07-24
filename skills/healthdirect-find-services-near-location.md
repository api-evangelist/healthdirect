---
name: Find health services near a location
description: Authenticate to the NHSD FHIR API and find healthcare services near a patient's location, filtered by service type and opening hours.
api: NHSD FHIR API
source: collections/nhsd-developers-portal.postman_collection.json
operations:
  - "POST /iam/oauth/token"
  - "GET /HealthcareService"
---

# Find health services near a location

Use the National Health Services Directory (NHSD) FHIR API to locate healthcare services close to a patient, backed by 400,000+ authoritative records.

## Prerequisites
- NHSD onboarding complete; you hold a `client_id`, `client_secret`, and `x-api-key`.
- Base URL: `https://api.fhir.nhsd.healthdirect.org.au/v4` (production) or `https://api.fhir.int.nhsd.healthdirect.org.au/v4` (integrator test).

## Steps
1. **Get an access token.** `POST https://iam.int.nhsd.healthdirect.org.au/iam/oauth/token` with header `x-api-key: <apiKey>` and form body `grant_type=client_credentials&client_id=<id>&client_secret=<secret>`. Read `accessToken` from the JSON response.
2. **Search by proximity.** `GET {base}/HealthcareService?location.physicalType=si&location.near=<lat>:<lng>&location.near-distance=5000|http://unitsofmeasure.org|m` with headers `x-api-key` and `Authorization: Bearer <accessToken>`. Results come back nearest-first (each carries a `proximity-distance` extension).
3. **Narrow by service type** (optional). Add `&service-type=nhsd:/reference/taxonomies/snomed-servicetype|<snomedCode>`. Combine multiple types OR-wise with a comma-separated list.
4. **Filter to open now** (optional). Add `&openNow=true` (or `openIn=<minutes>` / `openAt=<ISO-8601>`).
5. **Pull in the location detail.** Add `&_include=HealthcareService:location` so the searchset Bundle also contains each service's `Location` (address, suburb, postcode, state).
6. **Page** through the FHIR searchset `Bundle` via the `Bundle.link` `next` relation.

## Rules
- Every request needs BOTH the `x-api-key` header and the `Authorization: Bearer` token.
- On `401`, the token expired — repeat step 1. On `403`, check credentials (and note the API is geo-restricted to Australia). On `404`, no records matched — broaden the criteria.
- This surface is read-only (GET); there is no write/idempotency contract.
- See `conventions/healthdirect-conventions.yml` and `errors/healthdirect-problem-types.yml`.
