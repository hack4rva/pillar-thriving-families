> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Research Notes — Thriving Families Pillar

Richmond Civic Hackathon | March 27–29, 2026
Last updated: 2026-03-18 (Parallel.ai verification pass incorporated)

---

## Executive Brief

**Status: Web-verified 2026-03-18**

The Thriving Families pillar addresses two interconnected problem areas for Richmond families: youth employment pathways and maternal/child health navigation. This brief reflects confirmed data sources and corrected figures as of the Parallel.ai verification pass on 2026-03-18.

### Youth Employment

Summer 2026 programming is active and operating on strict timelines. Hackathon solutions must account for real application windows:

- **Camp Diva Leadership Academy** (Girls For A Change): June 1 – July 10, 2026; rising 6th–9th grade self-identifying Black girls; $30 registration fee (scholarships available); applications open March 1, close May 15 or when full; scholarship applications close April 15. Location: 100 Buford Rd, North Chesterfield VA. Source: https://girlsforachange.org/events-and-programs/camp-diva-leadership-academy/
- **BGCMR Summer Day Camps**: Rising 6th–12th grade; 9 weeks; free; registration opens April, typically fills by May. Petersburg Club: Mon–Thu 9am–5pm; MLK Club: Mon–Thu 9am–4pm. Source: https://www.bgcmr.org/summer-programming
- **Youth Works RVA** (OCWB): FY26 applications open; ages 14–24; closing date not listed on page — contact ocwb-yes@rva.gov to confirm before March 27.

Virginia work permit rules: ages 14–15 require an Employment Certificate (electronic or paper, reviewed within 24 hours); ages 16–17 have hour restrictions but do not need a permit. Source: https://doli.virginia.gov/labor-law/youth-employment/

Note: The older DOLI URL `/child-labor/` returns a 404 error and must not be used in any materials.

### Maternal and Child Health

**Critical correction**: The VDH HealthStats portal (https://apps.vdh.virginia.gov/HealthStats/stats.htm) provides data only through 2020 for most indicators. Teams must use the **VDH Maternal & Child Health Dashboard** (https://www.vdh.virginia.gov/data/maternal-child-health/) as the primary source for current data.

VDH MCH Dashboard 2023 indicators (last updated October 10, 2025):
- 92,639 live births
- 9.8% preterm birth rate
- 5.8 infant deaths per 1,000 live births
- 34.5 maternal deaths per 100,000 live births (2019–2023 period)

Note: These are statewide Virginia figures. Richmond-city-specific maternal mortality is not confirmed at this time.

### ACS Table Code Correction

All repository materials must use **B17001** (Poverty Status in the Past 12 Months by Sex by Age) for poverty data. The code **C17001 does not exist** in ACS 5-year data and will return a 404 API error.

Confirmed valid ACS table codes:
- B27001 — Health Insurance Coverage Status by Sex by Age
- B01001 — Sex by Age
- B17001 — Poverty Status in the Past 12 Months by Sex by Age (replaces incorrect C17001)

### Census API Rate Limits

Unauthenticated users are limited to 500 queries per day per IP address (up to 50 variables per query). Teams sharing a proxy or firewall share this limit. All teams must register for a free Census API key at https://api.census.gov/data/key_signup.html before the hackathon begins.

### Education and Chronic Absenteeism

The VDOE School Climate Reports page (https://www.doe.virginia.gov/data-policy-funding/data-reports/data-collection/special-education) provides Chronic Absenteeism XLSX data at State, Division, and School levels for academic years 2015-16 through 2024-25. This is a valid proxy metric for family stability and health context. Teams should snapshot the 2024-2025 files into their repositories rather than querying VDOE live during the hackathon.

### Geographic Scope Warning

All claims must refer to City of Richmond (FIPS 51760), not the Richmond metro or MSA. MSA-level numbers will be inflated. Teams must enforce GEOID-level filters in all data pulls.

---

## Key Risks

- **Recency gap**: Mixing 2020 HealthStats data with 2023 MCH Dashboard data creates analytical inconsistencies. Teams must declare data vintage for every metric displayed.
- **Stale program info**: Youth employment tools displaying outdated program dates/eligibility are harmful to families relying on them.
- **Work permit accuracy**: Errors in work permit guidance could harm teens. Link to official DOLI source; do not paraphrase eligibility rules without legal review.
- **COPPA**: Any tool touching users under 13 must not collect personal data.
- **API quota**: Without Census API keys, demo-day rate limiting is a near-certain failure mode.

---

## Data Sources Quick Reference

| Source | URL | Format | Current as of |
|--------|-----|--------|---------------|
| GRTC GTFS | https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip | ZIP | Periodic |
| DOLI Youth Employment | https://doli.virginia.gov/labor-law/youth-employment/ | HTML | As updated |
| Camp Diva (Girls For A Change) | https://girlsforachange.org/events-and-programs/camp-diva-leadership-academy/ | HTML | Seasonal |
| BGCMR Summer Programming | https://www.bgcmr.org/summer-programming | HTML | Seasonal |
| VDH MCH Dashboard (primary) | https://www.vdh.virginia.gov/data/maternal-child-health/ | Embedded/CSV | 2023 (Oct 2025) |
| VDH HealthStats (historical) | https://apps.vdh.virginia.gov/HealthStats/stats.htm | PDF/Excel | Through 2020 |
| VDOE Chronic Absenteeism | https://www.doe.virginia.gov/data-policy-funding/data-reports/data-collection/special-education | XLSX | Through 2024-25 |
| Kids Count Data Center | https://datacenter.aecf.org/ | CSV (via UI) | Varies |
| Census API (ACS) | https://api.census.gov/ | JSON | Ongoing |

---

## Prototype Disclaimer

This tool provides general information and links to official resources. It does not provide legal advice or determine eligibility. For official determinations, consult the City of Richmond or relevant agency.
