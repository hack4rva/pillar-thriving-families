# Evidence Log

## Purpose
Log every verified fact, likely claim, and gap here. Cite official sources with URLs and access dates. This file is the source of truth for your project's credibility.

Last updated: 2026-03-18 via web verification pass.

---

## Format
Each entry: ID | Claim | Official URL | Date Accessed | Status | Notes

| ID | Claim | Official URL | Access Date | Status | Notes |
|----|-------|-------------|------------|--------|-------|
| E-001 | GRTC GTFS feed is publicly downloadable as a ZIP file | https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip | 2026-03-18 | Confirmed | 3.9 MB ZIP containing agency.txt, calendar.txt, routes.txt, shapes.txt, fare_attributes.txt, frequencies.txt; no authentication required |
| E-002 | GRTC website lists GTFS download link in footer | https://www.ridegrtc.com/ | 2026-03-18 | Confirmed | Footer links directly to gtfs.zip; also links to https://gtfs.org/ for spec documentation |
| E-003 | OCWB YES program Youth Works RVA is open for FY26 applications | https://www.rva.gov/community-wealth-building/youth-engagement-services | 2026-03-18 | Confirmed | Application described as open; closing date not listed on page; contact 804-646-7933 or ocwb-yes@rva.gov |
| E-004 | Youth Works RVA serves ages 14–24 across five tracks | https://www.rva.gov/community-wealth-building/youth-engagement-services | 2026-03-18 | Confirmed | Tracks: TRIP, Counselors in Training, Virtual Earn and Learn, In-Person Program, Founders Mark Program; 8-week summer program |
| E-005 | OCWB YES Forward program serves ages 18–24 | https://www.rva.gov/community-wealth-building/youth-engagement-services | 2026-03-18 | Confirmed | Covers healthcare, skilled trades, public safety, manufacturing, human services, IT |
| E-006 | OCWB Youth L.E.A.D.S. program serves ages 14–19, runs October–April | https://www.rva.gov/community-wealth-building/youth-engagement-services | 2026-03-18 | Confirmed | 13-week introductory leadership program |
| E-007 | OCWB Youth Empowerment Council serves ages 14–19, runs October–April | https://www.rva.gov/community-wealth-building/youth-engagement-services | 2026-03-18 | Confirmed | 13-week advanced leadership program |
| E-008 | Girls For A Change Girl Action Teams serves grades 6–12 | https://www.girlsforachange.org/programs | 2026-03-18 | Confirmed | Free community programs; youth identify community challenges and create solutions |
| E-009 | Girls For A Change Girl Ambassador Program (GAP) serves grades 9–12 | https://www.girlsforachange.org/programs | 2026-03-18 | Confirmed | 4-year workforce development initiative; job readiness and professional skills |
| E-010 | Girls For A Change Immersion Lab serves grades 9–12 | https://www.girlsforachange.org/programs | 2026-03-18 | Confirmed | Business incubator; entrepreneurship and creative industry skills |
| E-011 | Girls For A Change Camp Diva Leadership Academy serves grades 6–8 | https://www.girlsforachange.org/programs | 2026-03-18 | Confirmed | Summer program; 2025 dates were June 23 – August 1 (2026 dates not yet posted at time of check) |
| E-012 | Girls For A Change Peer Advisor program serves grades 9–12 with monthly stipend | https://www.girlsforachange.org/programs | 2026-03-18 | Confirmed | Peer advisors provide guidance and mentorship to peers |
| E-013 | Girls For A Change after-school programs serve grades 1–8 with STEAM and tutoring | https://www.girlsforachange.org/programs | 2026-03-18 | Confirmed | Located at Chesterfield headquarters; includes social-emotional wellness |
| E-014 | Boys & Girls Clubs of Metro Richmond serves youth ages 11–24 | https://www.bgcmr.org/programs | 2026-03-18 | Confirmed | Year-round out-of-school-time programs; after-school during school year, all-day in summer |
| E-015 | Virginia work permit (Employment Certificate) required only for ages 14–15 | https://doli.virginia.gov/labor-law/youth-employment/ | 2026-03-18 | Confirmed | Ages 16–17 have restrictions but do not need an Employment Certificate |
| E-016 | Virginia Employment Certificate available via electronic system reviewed within 24 hours | https://doli.virginia.gov/labor-law/youth-employment/ | 2026-03-18 | Confirmed | Three-party registration: youth, employer, parent/guardian |
| E-017 | Manual work permit process requires two forms: Permission to Employ and Employer Intent to Employ | https://doli.virginia.gov/labor-law/youth-employment/ | 2026-03-18 | Confirmed | Mail to DOLI Child Labor Division, 1570 Parham Road, Richmond VA 23228; phone 804-371-3104 ext. 242 |
| E-018 | VDH publishes birth and maternal health statistics at HealthStats portal | https://apps.vdh.virginia.gov/HealthStats/stats.htm | 2026-03-18 | Confirmed | Data available in PDF and Excel formats; live births, low-weight births, teenage pregnancies, infant deaths (1995–2020/2022 depending on dataset) |
| E-019 | ACS table B27001 (Health Insurance Coverage Status by Sex by Age) exists and is accessible via Census API | https://api.census.gov/data/2022/acs/acs5/variables/B27001_001E.json | 2026-03-18 | Confirmed | Variable B27001_001E returns concept "Health Insurance Coverage Status by Sex by Age"; universe is civilian noninstitutionalized population |
| E-020 | ACS table B01001 (Sex by Age) exists and is accessible via Census API | https://api.census.gov/data/2022/acs/acs5/variables/B01001_001E.json | 2026-03-18 | Confirmed | Variable B01001_001E returns concept "Sex by Age"; integer type with margin of error attributes |
| E-021 | ACS table B17001 (Poverty Status in the Past 12 Months by Sex by Age) exists via Census API | https://api.census.gov/data/2022/acs/acs5/groups/B17001.json | 2026-03-18 | Confirmed | Concept confirmed as "Poverty Status in the Past 12 Months by Sex by Age"; note: VERIFICATION_TODO referenced C17001 which does NOT exist — correct table code is B17001 |
| E-022 | C17001 ACS table code does NOT exist in 2022 or 2023 ACS 5-year data | https://api.census.gov/data/2022/acs/acs5/groups.json | 2026-03-18 | Confirmed | API returns 404 for C17001 group and variable lookups in both 2022 and 2023 ACS5; correct poverty table is B17001 |
| E-023 | Census API key signup is at api.census.gov/data/key_signup.html | https://api.census.gov/data/key_signup.html | 2026-03-18 | Confirmed | Valid .gov page titled "Request a U.S. Census Data API Key"; requires ToS agreement |
| E-024 | Kids Count Data Center moved to datacenter.aecf.org (redirect from datacenter.kidscount.org) | https://datacenter.aecf.org/ | 2026-03-18 | Confirmed | datacenter.kidscount.org returns 301 redirect to datacenter.aecf.org; platform claims data download by state, county, and city |
| E-025 | Kids Count Data Center claims CSV download by state, county, and city | https://datacenter.aecf.org/ | 2026-03-18 | Likely | Site text states "download data by state, county, and city" but specific CSV format and Richmond availability not confirmed via automated fetch; manual verification recommended |

---

## Confirmed
(Facts with verified official sources — see table above)

Key confirmed facts:
- GRTC GTFS ZIP is live and freely downloadable at the URL above (E-001)
- OCWB YES programs are active with FY26 applications open; Youth Works RVA ages 14–24 (E-003, E-004)
- Virginia work permits required only for ages 14–15; not required for 16–17 (E-015)
- ACS tables B27001 and B01001 confirmed; correct poverty table is B17001 (not C17001 as listed in TODO) (E-019 to E-022)
- Census API key signup URL is correct (E-023)

---

## Likely but Unverified
- Kids Count Virginia CSV download confirmed by site text but format/Richmond access not directly tested (E-025)
- VDH HealthStats data exists in Excel for some datasets but maternal mortality as a distinct download not confirmed (E-018)
- Girls For A Change Camp Diva 2026 dates not yet posted; 2025 dates used as reference (E-011)

---

## Missing
(Critical gaps that block accurate claims)
- Youth Works RVA Summer 2026 application closing date (page says open but no close date listed)
- VDH maternal mortality rate for City of Richmond (current year) — HealthStats page has birth/infant data but not a standalone mortality download URL
- Exact column structure of VDH HealthStats Excel files (requires manual download and inspection)
- Kids Count Virginia: whether Richmond city (independent city) is separately filterable from metro area — requires manual testing
- BGCMR specific program names beyond general categories (academic support, leadership, recreation)

---

## Table Code Correction — ACTION REQUIRED
The VERIFICATION_TODO and some research files reference **C17001** as the ACS poverty table code. This is **incorrect**.

- C17001 does NOT exist in ACS 5-year data (API returns 404)
- Correct table: **B17001** — "Poverty Status in the Past 12 Months by Sex by Age"
- All team materials referencing C17001 should be updated to B17001

---

## Useful Datasets
(Data sources identified; verified access noted)

| Dataset | URL | Format | Verified |
|---------|-----|--------|---------|
| GRTC GTFS | https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip | ZIP (CSV text files) | Yes — live download confirmed |
| ACS B27001 Health Insurance | https://api.census.gov/data/2022/acs/acs5 | API (JSON) | Yes — variable confirmed |
| ACS B01001 Sex by Age | https://api.census.gov/data/2022/acs/acs5 | API (JSON) | Yes — variable confirmed |
| ACS B17001 Poverty Status | https://api.census.gov/data/2022/acs/acs5 | API (JSON) | Yes — group confirmed |
| VDH HealthStats (births, infant deaths) | https://apps.vdh.virginia.gov/HealthStats/stats.htm | PDF and Excel | Yes — page confirmed, formats listed |
| Kids Count Data Center | https://datacenter.aecf.org/ | CSV (claimed) | Likely — redirect confirmed, CSV not directly tested |

---

## Useful Source Documents
(Documents that support content curation)
- DOLI Youth Employment page: https://doli.virginia.gov/labor-law/youth-employment/
- OCWB YES program page: https://www.rva.gov/community-wealth-building/youth-engagement-services
- Girls For A Change programs: https://www.girlsforachange.org/programs
- BGCMR programs: https://www.bgcmr.org/programs

---

## Prior Art
(National comparables; see `03_artifacts/benchmark_scan.md` for details)
- YouthWorks Boston — centralized youth employment portal
- March of Dimes Peristats — maternal health indicator dashboard
- County Health Rankings — consistent indicator definitions

---

## Risks
- Youth employment tool may display stale program information if not maintained
- Maternal health dashboard may use different data vintage than official agency reports
- Work permit guidance must be accurate; errors could harm teens who rely on it
- Any tool touching minor users must comply with COPPA (no data collection from under 13)
- ACS table code C17001 does not exist — teams using this code will receive API errors; use B17001 instead
