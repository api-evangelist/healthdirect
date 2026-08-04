# Healthdirect Australia (healthdirect)

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

Healthdirect Australia is a national, government-owned, not-for-profit organisation that operates core Australian digital-health infrastructure and consumer health services on behalf of the Commonwealth, states, and territories. Its developer surface is the National Health Services Directory (NHSD) — the authoritative national directory of 400,000+ health service and practitioner records — exposed to government, commercial, and clinical software developers through standards-based HL7 FHIR APIs, an embeddable search widget, and a Provider Appointments API.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/healthdirect/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/healthdirect/refs/heads/main/apis.yml)

## Tags

- Healthcare
- Australia
- FHIR
- HL7
- Interoperability
- Provider Directory
- National Health System
- Health Services Directory
- Telehealth
- Digital Health
- Appointments

## Timestamps

- **Created:** 2026-07-24
- **Modified:** 2026-07-24

## APIs

### NHSD FHIR API

Real-time, read-only HL7 FHIR API over the National Health Services Directory, aligned to the HL7 AU Provider Directory (AU-PD) implementation guide. Queries Organization, HealthcareService, PractitionerRole, and Practitioner resources — including geospatial, open-now, service-type (SNOMED CT-AU), and identifier searches. Secured with OAuth 2.0 client-credentials plus an `x-api-key` header.

- **Human URL:** [NHSD Integration & Documentation](https://about.healthdirect.gov.au/what-we-do/portfolio/nhsd/integration-hub/documentation)
- **Base URL:** `https://api.fhir.int.nhsd.healthdirect.org.au/v4` (integrator test environment)
- [FHIR Implementation Guide v4](https://build.fhir.nhsd.healthdirect.org.au/v4/index.html) (geo-restricted to Australia)
- [Postman Collection](collections/nhsd-developers-portal.postman_collection.json)

### NHSD FHIR Bulk Data Export

Read-only HL7 FHIR bulk data export for retrieving large NHSD datasets at a specified frequency.

- **Human URL:** [Bulk exports guide](https://build.fhir.nhsd.healthdirect.org.au/v4/bulkexports.html)

### NHSD FHIR Ingestion & Data Acquisition Hub

HL7 FHIR write/inbound interface for approved data-contributing sources to submit and maintain directory records.

- **Human URL:** [Ingestion hub guide](https://build.fhir.nhsd.healthdirect.org.au/ingestion/index.html)

### NHSD Provider Appointments API

Surfaces real-time appointment availability and booking from certified provider booking platforms (AutoMed, HealthEngine, HotDoc, MedAdvisor, Medi2Apps).

- **Human URL:** [NHSD Integration & Documentation](https://about.healthdirect.gov.au/what-we-do/portfolio/nhsd/integration-hub/documentation)

### NHSD Search Widget

Embeddable, responsive NHSD search component for websites and mobile apps.

- **Human URL:** [Widget implementation guide](https://media.healthdirect.org.au/publications/NHSD_widget-implementation-guide.pdf)
- **Base URL:** `https://widget.nhsd.healthdirect.org.au/v1/widget/search`

## Standards & Auth

- **FHIR:** HL7 AU Provider Directory (AU-PD), FHIR R4
- **Terminology / addressing:** SNOMED CT-AU, G-NAF
- **Auth:** OAuth 2.0 client-credentials + `x-api-key`
- **Access:** Gated — integration requires Integrator Test Environment registration, production registration, and an NHSD Agreement (not self-serve)

## Links

- **Developer Portal:** [NHSD Integration Hub](https://about.healthdirect.gov.au/what-we-do/portfolio/nhsd/integration-hub)
- **Getting Started:** [Onboarding](https://about.healthdirect.gov.au/what-we-do/portfolio/nhsd/integration-hub/getting-started)
- **Support:** [Technical support](https://about.healthdirect.gov.au/what-we-do/portfolio/nhsd/integration-hub/technical-support)
- **Consumer site:** [healthdirect.gov.au](https://www.healthdirect.gov.au/)
