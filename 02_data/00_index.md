# Data Index - Thriving Families

## Status warning
This pillar has significant data readiness challenges.
- Youth Employment (D3=1): No compiled dataset exists. Teams must curate content.
- Maternal Health (D3=3): Four named public sources exist but access methods are unverified.

Before building, verify each source below. Log confirmed access in `02_data/source_inventory.csv`.

---

## Youth Employment — Data Sources

### Virginia Department of Labor and Industry (DOLI) — Youth Labor Laws
- What: Virginia Code on employment of minors; work permit requirements; prohibited occupations; hours restrictions by age
- Expected URL: https://www.doli.virginia.gov/ (verify child labor section)
- Format: Web pages, PDF regulations
- Access: Public
- Readiness: High — law is stable and publicly available
- Use: Plain-language summary for teens and employers; compliance checklist

### Office of Community Wealth Building (OCWB) — Youth Programs
- What: City of Richmond office that administers workforce and youth employment programs
- Expected URL: https://www.rva.gov/community-wealth-building (verify)
- Format: Web pages; program descriptions (PDF likely)
- Access: Public
- Readiness: Medium — programs exist but no structured dataset; manual curation required
- Use: Program directory entries; eligibility and application window info

### Girls For A Change
- What: Richmond nonprofit providing youth leadership and workforce development programs
- Contact reference: Angela Patton (named in rubric as potential champion)
- URL: https://girlsforachange.org/ (verify)
- Format: Website; program pages
- Access: Public
- Readiness: Medium — web content available; no API
- Use: Program listing; eligibility; contact info

### Richmond Education Fund (YouthWork Richmond)
- What: Youth employment program; Taikein Cooper named in rubric as potential champion
- URL: Verify via Richmond Education Fund or YouthWork Richmond search
- Format: Website
- Access: Public
- Readiness: Low — URL unverified
- Use: Program listing

### Boys & Girls Club of Metro Richmond
- What: Youth workforce and career readiness programs
- Contact reference: Sean Miller (named in rubric as potential champion)
- URL: https://bgcmr.org/ (verify)
- Format: Website
- Access: Public
- Readiness: Medium
- Use: Program listing

### GRTC Transit Routes
- What: Greater Richmond Transit Company route and schedule data
- URL: https://ridegrtc.com/ and GTFS feed (verify)
- Format: GTFS (General Transit Feed Specification) — structured
- Access: Public; GTFS typically available as download
- Readiness: High — GTFS is standard and publicly available
- Use: Overlay employer/program locations with transit access; identify transportation gaps

### Richmond Open Data Portal
- What: City of Richmond open data catalog
- URL: https://rvaopendata.org/ (verify)
- Format: Socrata/CSV/API
- Access: Public
- Readiness: Low for youth employment — no workforce/youth employment section documented
- Use: Cross-reference if any youth or workforce datasets are added

---

## Maternal Health — Data Sources

### Virginia Department of Health (VDH) — Maternal Health Data
- What: Birth outcomes, maternal mortality, prenatal care, infant health indicators by geography and race
- Expected URL: https://www.vdh.virginia.gov/vital-records/ or https://www.vdh.virginia.gov/data/ (verify)
- Format: Web tables, downloadable data files (CSV/Excel likely)
- Access: Public
- Readiness: Medium — data exists but format and granularity need verification
- Use: Core maternal health indicators; racial disparity metrics; Richmond-specific filtering

### American Community Survey (ACS) — Census Bureau
- What: Population demographics, income, insurance coverage, poverty, education by geography
- URL: https://data.census.gov/ (verified as stable)
- Format: API (Census API), CSV download, web tables
- Access: Public; API requires free key
- Readiness: High — well-documented, stable API
- Use: Population denominators; insurance coverage; poverty rates; demographic context

### Kids Count Virginia — Annie E. Casey Foundation
- What: Child and family wellbeing indicators; health, education, economic wellbeing by state and locality
- URL: https://datacenter.kidscount.org/ (verify Virginia section)
- Format: Web tables; CSV download
- Access: Public
- Readiness: High — stable platform with download functionality
- Use: Child health indicators; family economic context; Richmond comparison data

### Virginia Department of Education (VDOE) — School Data
- What: Enrollment, free/reduced lunch eligibility, student demographic data
- URL: https://www.doe.virginia.gov/data-policy-funding/data-reporting (verify)
- Format: CSV, Excel reports
- Access: Public
- Readiness: Medium — data exists; format varies by report
- Use: School-age population context; economic vulnerability proxy

---

## Cross-Cutting Notes

All four maternal health sources are public and should be verifiable before the hackathon.
Teams choosing maternal health should spend 2–3 hours verifying access and downloading sample data before Saturday build time.

Youth employment teams should plan to curate a program list manually from websites.
A curated JSON or CSV of 10–15 programs is a sufficient data foundation for a weekend MVP.
Do not wait for an official dataset that does not exist.
