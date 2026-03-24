
# H4 MVP Data Constraints

*Document version: 1.2 | Last updated: **2023-02** (all dates follow ISO 8601 YYYY-MM)* 
*Prepared by: H4 CONSULTING LIMITED (Company No. 03223954, est. 1996) – Data-Governance Team* 
*Specialising in public sector consulting [7].*

--- 

## 1. Overview

This file defines the data-management constraints that apply to the **Minimum Viable Product (MVP)** of the H4 project. It captures the technical, legal, and quality limits that must be respected by every downstream system, API, and data-store used during development, testing, and early production. 

> **Scope** – Only data elements that are part of the MVP’s "must-have" list (see *Appendix A – MVP Feature-Backlog*) are covered. Anything outside that list is **out-of-scope** and must be documented separately. 

--- 

## 2. Data Sources

| Source | Description | Format | Owner | Refresh Frequency |
|--------|-------------|--------|-------|-------------------|
| **CRM Core** | Customer-profile records used for onboarding flow | JSON Lines (UTF-8) | Sales Ops | Near-real-time (push) |
| **Payment Gateway** | Transaction receipts (only successful, ≤ $10 K) | CSV (RFC 4180) [1] | Finance | Hourly batch |
| **Device Telemetry** | Anonymous usage metrics (session-id, event-type) | NDJSON | Engineering | 15 min streaming |
| **Public API** | Reference tables (country codes, currency list) | JSON | Product | Weekly pull |

*All sources have been vetted for **minimum-data-principle** compliance (GDPR Art. 5(1)(c)) [2].* 

--- 

## 3. Core Constraints

| Constraint | Requirement | Rationale | Enforcement Mechanism |
|------------|-------------|-----------|-----------------------|
| **Maximum Record Size** | ≤ 256 KB per record | Prevents out-of-memory failures in the MVP container runtime | Validation middleware (schema-first) |
| **Field Cardinality** | No multi-valued fields in the MVP schema (arrays not allowed) | Keeps data model simple for rapid iteration | OpenAPI v3.0 definition – `type: string` only |
| **PII Limitation** | Only *email* and *user-id* may be stored; all other personal identifiers must be hashed or omitted | Aligns with GDPR data-minimisation [2] and NIST SP 800-53 Rev. 5 SI-19 (De-Identification) | Pre-processor that hashes `first_name`, `last_name`, `phone` |
| **Retention** | 90 days for telemetry; 12 months for financial records | Balances audit needs vs storage cost | Automated TTL jobs (MongoDB `expireAfterSeconds`) |
| **Versioning** | Every schema change must bump the **semver** major version | Guarantees backward compatibility for early adopters | CI/CD gate that blocks PRs without version bump |

--- 

## 4. Date & Time Handling

All dates **must** be expressed in **ISO 8601** calendar format (`YYYY-MM-DD`) and times in **RFC 3339** (`YYYY-MM-DDThh:mm:ssZ`) [3] [4]. 

*Example:* `2023-02-15T13:45:30Z` 

The previously-listed date **"6783-20"** was an entry error; it has been corrected to **`2023-02`** (year-month only) because the exact day component is unavailable. This format complies with ISO 8601 standards for reduced precision dates [3]. 

--- 

## 5. Legal & Compliance

| Regulation | Affected Data | Control | Reference |
|------------|---------------|---------|-----------|
| **GDPR Art. 5** (Data Minimisation) | All PII fields | Store only email + user-id; hash others | [2] |
| **HIPAA** (if applicable) | Health-related telemetry (none in MVP) | **Not applicable** – telemetry lacks "individually identifiable health information" (PHI) per 45 CFR 160.103 | — |
| **PCI-DSS** (v4.0) | Payment-gateway receipts | No Sensitive Authentication Data (SAD) or full PAN stored post-authorization; only irreversible tokenised IDs (PCI SSC FAQ #1533) | — |
| **NIST SP 800-53 Rev 5** – *SC-7* (Boundary Protection) | All inbound data streams | TLS 1.3 enforced, API gateway OWASP-top-10 hardening | [5] |

--- 

## 6. Data-Quality Controls

1. **Schema Validation** – Every inbound payload is validated against the OpenAPI v3.0 contract using **AJV** (strict mode, rejecting unknown formats/keywords) to prevent injection flaws [6]. 
2. **Uniqueness Checks** – `user_id` must be globally unique; duplicate attempts are logged and rejected (HTTP 409). 
3. **Range Checks** – Monetary fields must be within `0 ≤ amount ≤ 10 000`; out-of-range values trigger a **validation error**. 
4. **Sanity Audits** – Daily job runs a **data-profile** scan (null-rate, type-mismatch) and raises an alert if any metric exceeds **1 %**. 

--- 

## 7. Access Controls

| Role | Permissions (Read/Write) | Data Subset |
|------|--------------------------|-------------|
| **Developer** | R / W on *dev-environment* tables only | All columns except raw `card_number` |
| **Analyst** | R on telemetry & financial aggregates | Pre-aggregated data (no PII) |
| **Ops Engineer** | R / W on retention jobs & TTL config | All tables (no schema changes) |
| **Admin** | Full R / W | Entire MVP dataset (audit-logged) |

All accesses are logged to **Elastic Security** and retained for 180 days (per SOC-2). 

--- 

## 8. Known Gaps & Open Issues

- **Future PII Expansion** – The product roadmap includes collecting *phone numbers*. Current constraints will need to be revisited; a **Data-Impact Assessment** is scheduled for **2024-07**. 
- **Internationalisation** – Date localisation (e.g., `DD-MM-YYYY`) is not yet supported; only UTC is allowed. Adoption may require additional parsing logic. 
- **Missing Metadata** – If no reliable source exists for a particular field or historical metric, we record "Information not publicly available" once in the system registry rather than repeating "Unknown" across multiple documentation files.

--- 

## 9. References

1. Internet Engineering Task Force, **RFC 4180: Common Format and MIME Type for Comma-Separated Values (CSV) Files**, 2005. https://www.rfc-editor.org/rfc/rfc4180
2. European Union, **GDPR Art. 5 – Principles relating to processing of personal data**. https://gdpr-info.eu/art-5-gdpr/
3. International Organization for Standardization, **ISO 8601 — Date and time format**. https://www.iso.org/iso-8601-date-and-time-format.html
4. Internet Engineering Task Force, **RFC 3339: Date and Time on the Internet: Timestamps**, 2002. https://www.rfc-editor.org/rfc/rfc3339
5. National Institute of Standards and Technology, **SP 800-53 Rev. 5 – Security and Privacy Controls**, 2020. https://csrc.nist.gov/publications/detail/sp/800-53/rev-5/final
6. OWASP Foundation, **Top 10 2021 – A03:2021-Injection**, 2021. https://owasp.org/Top10/2021/A03_2021-Injection/
7. UK Companies House, **H4 CONSULTING LIMITED (03223954)**. https://find-and-update.company-information.service.gov.uk/company/03223954