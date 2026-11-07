> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Verification Research Results

Pillar: Thriving Families (youth employment, maternal health, Richmond, VA)
Date: 2026-03-18
Parallel.ai run_id: trun_3cad0ebea15c480e82b73b7784d0f0d8
Processor: pro

---

# Unblocking Richmond's Hackathon: Verified Data Sources and Immediate Actions for Youth Jobs and Maternal Health

## Executive Summary

This report resolves critical data dependencies for the Richmond Thriving Families hackathon, transforming ambiguous requirements into build-ready pipelines. The most significant finding is a recency gap in maternal health data: while the originally targeted VDH HealthStats portal only provides locality data through 2020, the VDH Maternal & Child Health dashboards offer 2023 metrics and should be the primary source. 

For youth employment, summer 2026 programming windows are highly time-bound. Girls For A Change's Camp Diva applications open March 1 and close May 15, while Boys & Girls Clubs of Metro Richmond (BGCMR) offers free 9-week summer camps that typically fill by May. Hackathon teams must design their solutions around these real-world constraints. Finally, technical guardrails must be established immediately: the Census API limits unauthenticated users to 500 queries per day per IP, requiring teams to register for free keys to avoid demo-day rate limiting.

## Objectives and Success Criteria

To ensure hackathon teams can ship credible, reusable data pipelines by Day 1, organizers must freeze endpoints, correct known schema errors, and document all access constraints. "Hackathon-ready" means teams are not wasting hours hunting for CSVs or debugging 404 errors. By locking in verified sources for GRTC transit, VDOE absenteeism, VDH maternal health, and local youth programs, we provide a stable foundation for MVP development.

## Source Inventory and Access Methods

All core sources required for the Thriving Families pillar are currently reachable. Capturing their exact URLs, formats, and update cadences prevents surprises during the event.

### Verified Data Sources Overview

| Source | Topic | Official URL | Format | Auth / Rate Limits | Update Cadence | Verification Status |
|---|---|---|---|---|---|---|
| GRTC GTFS | Transit | https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip | ZIP | None | Periodic | CONFIRMED |
| DOLI Youth Employment | Legal | https://doli.virginia.gov/labor-law/youth-employment/ | HTML | None | As updated | CONFIRMED |
| Girls For A Change Camp Diva | Summer Program | https://girlsforachange.org/events-and-programs/camp-diva-leadership-academy/ | HTML | None | Seasonal | CONFIRMED |
| BGCMR Summer | Summer Program | https://www.bgcmr.org/summer-programming | HTML | None | Seasonal | CONFIRMED |
| VDH HealthStats | Vital Stats (Historical) | https://apps.vdh.virginia.gov/HealthStats/stats.htm | Excel/PDF | None | Annual | CONFIRMED |
| VDH Maternal & Child Health | Maternal/Child | https://www.vdh.virginia.gov/data/maternal-child-health/ | Embedded/CSV | None | Periodic | CONFIRMED |
| Kids Count Data Center | Child/Family | https://datacenter.aecf.org/ | Web UI/CSV | None | Varies | CONFIRMED |
| VDOE Chronic Absenteeism | Education | https://www.doe.virginia.gov/data-policy-funding/data-reports/data-collection/special-education | XLSX | None | Annual | CONFIRMED |
| Census API (ACS) | Socioeconomic | https://api.census.gov/ | JSON | 500 queries/day/IP without key | Ongoing | CONFIRMED |

The table above serves as the definitive source of truth for hackathon data ingestion. Teams should script health checks against these URLs and cache responses where possible.

## Youth Employment: Current Programs, Seasons, and Legal Constraints

Summer 2026 programming is active but operates on strict timelines. Solutions built during the hackathon must account for these application windows to be practically useful for Richmond families.

### Summer 2026 Programs with Dates and Eligibility

| Program | Organization | Eligibility | 2026 Dates & Hours | Application Window | Cost |
|---|---|---|---|---|---|
| Camp Diva Leadership Academy | Girls For A Change | Rising 6th-9th grade self-identifying Black girls | June 1 - July 10, 2026; Mon-Fri 7:30am - 6:00pm | Opens March 1, 2026; Closes May 15 or when full | $30 registration fee; scholarships available |
| Summer Day Camps | BGCMR | Rising 6th-12th grade | 9 weeks; Mon-Thu 9:00am-5:00pm (Petersburg) or 9:00am-4:00pm (MLK) | Opens in April; typically fills by May | Free |

Camp Diva Leadership Academy is confirmed to run from June 1 to July 10, 2026, at 100 Buford Road, North Chesterfield, VA [1]. Registration applications close on May 15th or when full, and scholarship applications close on April 15th [1]. BGCMR offers a 9-week summer day camp across 4 clubs in Richmond and 1 in Petersburg [2]. These programs are offered at no cost, and registration opens in April [3]. Hours vary by location, with the Petersburg Club operating Monday through Thursday from 9:00AM to 5:00PM [4], and the MLK Club operating Monday through Thursday from 9:00AM to 4:00PM [5].

### Legal and Compliance Snapshot

Permit rules differ significantly by age. The correct and active URL for the Department of Labor and Industry (DOLI) youth employment guidelines is `https://doli.virginia.gov/labor-law/youth-employment/`. The older `/child-labor/` endpoint returns a 404 error and must be removed from all repository documentation. Hackathon teams must include legal disclaimers when presenting work permit guidance.

### Transportation Enablement via GRTC GTFS

Transit-time matching is highly feasible using the current GRTC GTFS feed. Teams should geocode program sites (e.g., 100 Buford Rd for Camp Diva) and precompute transit-time isochrones to help families determine the accessibility of different summer programs.

## Maternal Health: 2023 Dashboards Supersede 2020 HealthStats Data

A critical correction for the hackathon teams: the VDH HealthStats portal provides historical data, but the VDH Maternal & Child Health dashboards offer much more recent metrics.

### Indicator Sources and Recency

The VDH HealthStats page provides "Live Births" totals by race and city/county, but the data only goes up to the year 2020 [6]. To access more current data, teams must use the VDH Maternal & Child Health Dashboards (`https://www.vdh.virginia.gov/data/maternal-child-health/`) [7]. As of its last update on October 10, 2025, this dashboard provides 2023 indicators, including 92,639 live births, a 9.8% preterm birth rate, and 5.8 infant deaths per 1,000 live births [7]. It also reports 34.5 maternal deaths per 100,000 live births between 2019-2023 [7]. 

### ACS Codes for Contextual Indicators

| Topic | ACS Table Code | Status | Correction Notes |
|---|---|---|---|
| Health insurance coverage | B27001 | CONFIRMED | Valid table for Health Insurance Coverage Status by Sex by Age. |
| Poverty status | B17001 | CORRECTED | Replaces C17001, which does not exist in ACS 5-year data. |
| Sex by age | B01001 | CONFIRMED | Valid table for demographic denominators. |

Teams must update all repository materials referencing C17001 to B17001 to prevent API 404 errors during the hackathon.

### Kids Count Data Center Usage

The Kids Count Data Center (`https://datacenter.aecf.org/`) is CONFIRMED as a valid source for child and family well-being indicators [8] [9]. The platform provides a "Download Raw Data" option for specific indicators, allowing teams to extract CSV files [10] [11] [12]. Because this is a UI-driven download rather than a documented REST API, teams should plan to manually download the required CSVs prior to the event or write headless browser scripts.

## Education Linkages: Chronic Absenteeism as a Family Health Context Signal

Chronic absenteeism serves as a vital proxy metric for family stability and health. The Virginia Department of Education (VDOE) provides comprehensive data that teams can use to contextualize youth engagement.

The VDOE School Climate Reports page (`https://www.doe.virginia.gov/data-policy-funding/data-reports/data-collection/special-education`) is CONFIRMED as the official source for this data [13]. The site provides downloadable XLSX files for Chronic Absenteeism at the State, Division, and School levels for academic years ranging from 2015-2016 through 2024-2025 [13]. Because these are large Excel files updated on an "Ad Hoc" basis, teams should snapshot the 2024-2025 files into their repositories rather than querying the VDOE site live during the hackathon.

## Technical Implementation Plan

Standardizing ingestion methods and establishing API guardrails now will prevent catastrophic failures during demo day.

### API and Rate-Limit Strategy

| API / Feed | Limit / Constraint | Required Mitigation |
|---|---|---|
| Census API | 500 queries per IP address per day; up to 50 variables per query [14] [15] | Register for a free API key; batch variables; cache JSON responses to disk. |
| GRTC GTFS | None stated | Version snapshots; validate against GTFS spec. |
| Kids Count | UI-driven CSV download | Store downloaded CSVs with an `as_of` date in the repo. |
| VDOE XLSX | Large files; Ad Hoc updates | Hash files; retain versioned copies; parse with schema checks. |

The Census API strictly enforces a limit of 500 queries per IP address per day for unauthenticated users [14]. If multiple team members operate behind a single proxy or firewall, they will share this 500-query limit [14]. Teams must register for an API key at `https://api.census.gov/data/key_signup.html` to bypass this restriction.

### CI Guardrails

To maintain repository health, organizers should implement automated preflight checks. This includes a link validator to catch 404s (like the outdated DOLI link), a Census schema smoke test to fail builds if invalid table codes are used, and assertions to ensure critical fields (like application close dates) are present in the data models.

## Risk Register and Mitigations

Several risks threaten the viability of the hackathon outputs if not addressed immediately.

* **Ownership Risk:** The repository currently lacks a named departmental champion. Without securing a stakeholder like Angela Patton (Girls For A Change) or Sean Miller (BGCMR), there is no continuation pathway for the tools built.
* **Recency Risk:** Mixing 2020 HealthStats data with 2023 MCH Dashboard data will create analytical inconsistencies. Teams must explicitly declare the data vintage for every metric displayed.
* **Scope Creep:** Multiple sources report at different geographic levels (State, Division, MSA). Teams must strictly enforce GEOID-level filters for the City of Richmond (FIPS 51760) to avoid presenting inflated MSA numbers as city-specific data.

## Pre-Hackathon Action Checklist

Organizers must complete the following tasks before March 27, 2026:

* Contact `ocwb-yes@rva.gov` to confirm the exact application close date for Youth Works RVA FY26.
* Mandate that all data pods register for Census API keys.
* Download and snapshot the VDOE 2024-2025 Chronic Absenteeism XLSX files and create a data dictionary.
* Export the 2023 CSVs from the VDH MCH dashboards and document the column structures.
* Implement `sources.yml` and run the first automated health check against all verified URLs.

## Hackathon-Day Playbook

To minimize friction, organizers should provide teams with ready-to-run assets. This includes prebuilt Jupyter notebooks demonstrating Census ACS pulls for FIPS 51760 using the corrected B17001 table. A centralized data bundle containing the GRTC GTFS ZIP, VDOE XLSX files, VDH MCH CSV exports, and Kids Count CSV samples will allow teams to start building immediately without spending their first 12 hours on data wrangling.

## Post-Demo Verification and Sustainment

Following the event, the `evidence_log.md` must be updated with all new confirmations, URLs, and access dates established in this report. The `02_data/source_inventory.csv` should be populated with the verified access methods, formats, and update cadences. Finally, organizers must document the inaccuracies discovered during this verification pass (such as the C17001 table error and the DOLI URL change) to ensure future contributors do not repeat them.

## References

1. *Camp Diva Leadership Academy | Girls For A Change*. https://girlsforachange.org/events-and-programs/camp-diva-leadership-academy/
2. *SUMMER PROGRAMMING — Boys & Girls Clubs of Metro Richmond*. https://www.bgcmr.org/summer-programming
3. *The Summer Crunch - richmondmagazine.com*. https://richmondmagazine.com/life-style/leisure/affordable-summer-camps/
4. *Petersburg — Boys & Girls Clubs of Metro Richmond*. https://www.bgcmr.org/petersburg-club
5. *MLK — Boys & Girls Clubs of Metro Richmond*. https://www.bgcmr.org/mlk-club
6. *Statistical Reports and Tables*. https://apps.vdh.virginia.gov/HealthStats/stats.htm
7. *Maternal & Child Health - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/
8. *KIDS COUNT Data Center from the Annie E. Casey Foundation*. https://datacenter.aecf.org/
9. *KIDS COUNT Data Center from the Annie E. Casey Foundation*. https://datacenter.aecf.org/data
10. *Children in foster care | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/6243-children-in-foster-care
11. *Number of completed cases and children in founded reports and family assessments | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/10614-number-of-completed-cases-and-children-in-founded-reports-and-family-assessments
12. *Child care assistance participation after 2020 | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/11640-child-care-assistance-participation-after-2020
13. *
	
    School Climate Reports | Virginia Department of Education

*. https://www.doe.virginia.gov/data-policy-funding/data-reports/data-collection/special-education
14. *Census Data API User Guide*. https://www.census.gov/data/developers/guidance/api-user-guide.Help_&_Contact_Us.html
15. *Census Data API User Guide*. https://www2.census.gov/data/api-documentation/api-user-guide.pdf