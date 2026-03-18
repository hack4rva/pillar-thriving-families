# Verification TODO

This file tracks items that require verification before the hackathon (March 27–29, 2026) or during the event. Items marked CRITICAL block MVP development if unresolved.

Last verification pass: 2026-03-18 (web research agent). See `evidence_log.md` for full citations.

---

## Pre-Hackathon (Organizers / City Representatives)

### CRITICAL — Youth Employment
- [x] Compile starter data package: list of active Richmond youth employment programs with name, org, age eligibility, application window, location, website
  - **DONE** — See `03_artifacts/youth_programs_starter.md` (10 programs verified, 2026-03-18)
  - Remaining gap: Youth Works RVA application close date not listed on program page; contact ocwb-yes@rva.gov
- [ ] Name departmental champion: Angela Patton (Girls For A Change), Taikein Cooper (Richmond Ed Fund), or Sean Miller (Boys & Girls Club)
  - Without this: no continuation pathway after hackathon
- [ ] Add workforce/youth employment section to Richmond open data catalog (rvaopendata.org)

### IMPORTANT — Maternal Health
- [x] Verify and link VDH maternal health data URL and confirm download format (CSV, Excel, or API)
  - **DONE** — VDH HealthStats at https://apps.vdh.virginia.gov/HealthStats/stats.htm confirmed; formats are PDF and Excel; includes live births, low-weight births, infant deaths (1995–2020); maternal mortality not a standalone download
- [ ] Verify ACS table codes for Richmond maternal health indicators (uninsured, poverty, demographics)
  - **PARTIAL** — B27001 (health insurance) and B01001 (sex/age) confirmed. NOTE: C17001 (poverty) does NOT exist — correct code is **B17001** (Poverty Status in the Past 12 Months by Sex by Age). Update all materials referencing C17001.
- [x] Verify Kids Count Virginia data URL and confirm CSV download access
  - **DONE (Likely)** — datacenter.kidscount.org redirects to https://datacenter.aecf.org/; site claims CSV download by state/county/city; direct CSV test not completed; manual verification recommended before hackathon
- [x] Verify VDOE data source URL relevant to maternal/family health context
  - **DONE** — VDOE School Climate Reports at https://www.doe.virginia.gov/data-policy-funding/data-reports/data-collection/special-education confirmed 2026-03-18. Provides Chronic Absenteeism XLSX at State, Division, and School levels for 2015-16 through 2024-25. Chronic absenteeism is a valid proxy for family health context. See E-027.
- [ ] Specify expected output types in Maternal Health problem statement

---

## Hackathon Teams — Verify Before Building

### Youth Employment teams
- [x] Confirm GRTC GTFS download URL at https://ridegrtc.com/ (or developer resources page)
  - **CONFIRMED** — Direct download: https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip (3.9 MB ZIP; confirmed live 2026-03-18); footer of ridegrtc.com links to this URL; no authentication required
- [x] Confirm OCWB youth program current application windows (manual web check)
  - **CONFIRMED** — Youth Works RVA FY26 application is open; no close date posted. Contact 804-646-7933 or ocwb-yes@rva.gov. See `03_artifacts/youth_programs_starter.md`
- [x] Confirm Girls For A Change current program listings and age eligibility
  - **CONFIRMED** — 6 programs verified at girlsforachange.org/programs (2026-03-18): Girl Action Teams (gr. 6–12), GAP (gr. 9–12), Immersion Lab (gr. 9–12), Camp Diva (gr. 6–8), Mission in Bloom (rising 9th graders), Peer Advisor (gr. 9–12). After-school programs for gr. 1–8 also listed.
- [x] Confirm Boys & Girls Club Metro Richmond current program listings
  - **PARTIALLY CONFIRMED** — bgcmr.org confirms ages 11–24, year-round programming, after-school and all-day summer. Specific program names not listed on main site; contact (804) 359-5250 or development@bgcmr.org
- [x] Read DOLI child labor section and draft work permit plain-language summary
  - **CONFIRMED** — DOLI page at https://doli.virginia.gov/labor-law/youth-employment/ verified. Summary: ages 14–15 need Employment Certificate (electronic or paper); ages 16–17 have hour restrictions but no permit required. See `03_artifacts/youth_programs_starter.md` for plain-language table.
  - Note: DOLI URL /child-labor/ returns 404; correct URL is /labor-law/youth-employment/
- [x] Confirm which programs are active for Summer 2026 vs. year-round
  - **DONE** — Web-verified 2026-03-18: Youth Works RVA (summer, 14–24), BGCMR day camps (rising 6th–12th grade, free, 9 weeks, opens April), and Camp Diva (June 1 – July 10, 2026) all confirmed for Summer 2026. OCWB L.E.A.D.S. and Empowerment Council are October–April only (not summer). See E-011, E-014.

### Maternal Health teams
- [x] Obtain free Census API key at https://api.census.gov/data/key_signup.html (takes ~24 hours; do this before Friday)
  - **CONFIRMED** — URL is valid and active; page title "Request a U.S. Census Data API Key"; free registration, requires ToS agreement
- [x] Identify correct ACS table codes: B27001 (health insurance), C17001 (poverty), B01001 (age/sex)
  - **PARTIALLY CONFIRMED with CORRECTION:**
    - B27001 (Health Insurance Coverage Status by Sex by Age) — CONFIRMED ✓
    - B01001 (Sex by Age) — CONFIRMED ✓
    - **C17001 — DOES NOT EXIST** in ACS 5-year data (API returns 404)
    - **Correct poverty table: B17001** — "Poverty Status in the Past 12 Months by Sex by Age" — CONFIRMED ✓
    - ACTION: Update all repo materials that reference C17001 to B17001
- [ ] Download VDH maternal health data sample and inspect column structure
  - URL confirmed (https://apps.vdh.virginia.gov/HealthStats/stats.htm); manual download and column inspection still needed
- [ ] Download Kids Count Virginia CSV sample and inspect column structure
  - URL confirmed (https://datacenter.aecf.org/); CSV capability stated; manual download and column inspection still needed
- [x] Confirm which year's data is most current for each source
  - **DONE** — Web-verified 2026-03-18: VDH HealthStats data only reaches 2020 for most indicators. The VDH Maternal & Child Health Dashboard (https://www.vdh.virginia.gov/data/maternal-child-health/) provides 2023 data (last updated Oct 10, 2025) and is the recommended primary source. Teams must use MCH Dashboard, not HealthStats, for current indicators. See E-026.

---

## Content Accuracy Checks (All Teams)

- [ ] Work permit guidance: have someone with legal literacy review before demoing
  - Plain-language summary drafted in `03_artifacts/youth_programs_starter.md`; links to official DOLI source; legal review still recommended
- [ ] Program eligibility claims: link to official source; do not assert eligibility directly
- [ ] Maternal health statistics: verify each number against named source before displaying
- [ ] Any "Richmond-specific" claim: confirm it refers to City of Richmond, not Richmond metro or MSA

---

## Post-Demo Verification

- [x] Update `evidence_log.md` with all confirmed sources, URLs, and access dates
  - **DONE** — evidence_log.md updated with 28 entries (E-001 through E-028) incorporating Parallel.ai verification results from 2026-03-18. New entries: E-026 (VDH MCH Dashboard 2023), E-027 (VDOE chronic absenteeism), E-028 (Census API rate limits). Existing entries E-011, E-014, E-018, E-023 updated with verified details and official URLs.
- [ ] Update `02_data/source_inventory.csv` with verified access methods and field names
- [ ] Document any inaccuracies discovered during testing and how they were corrected
