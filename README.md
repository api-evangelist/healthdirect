# Healthdirect Australia (healthdirect)

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
