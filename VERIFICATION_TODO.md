# Verification TODO

This file tracks items that require verification before the hackathon (March 27–29, 2026) or during the event. Items marked CRITICAL block MVP development if unresolved.

---

## Pre-Hackathon (Organizers / City Representatives)

### CRITICAL — Youth Employment
- [ ] Compile starter data package: list of active Richmond youth employment programs with name, org, age eligibility, application window, location, website
  - Responsible: City representative (Amy Popovich, Eva Colen, or Jacque Hale) or named champion
  - Without this: teams must curate manually from program websites (2–3 hours)
- [ ] Name departmental champion: Angela Patton (Girls For A Change), Taikein Cooper (Richmond Ed Fund), or Sean Miller (Boys & Girls Club)
  - Without this: no continuation pathway after hackathon
- [ ] Add workforce/youth employment section to Richmond open data catalog (rvaopendata.org)

### IMPORTANT — Maternal Health
- [ ] Verify and link VDH maternal health data URL and confirm download format (CSV, Excel, or API)
- [ ] Verify ACS table codes for Richmond maternal health indicators (uninsured, poverty, demographics)
- [ ] Verify Kids Count Virginia data URL and confirm CSV download access
- [ ] Verify VDOE data source URL relevant to maternal/family health context
- [ ] Specify expected output types in Maternal Health problem statement

---

## Hackathon Teams — Verify Before Building

### Youth Employment teams
- [ ] Confirm GRTC GTFS download URL at https://ridegrtc.com/ (or developer resources page)
- [ ] Confirm OCWB youth program current application windows (manual web check)
- [ ] Confirm Girls For A Change current program listings and age eligibility
- [ ] Confirm Boys & Girls Club Metro Richmond current program listings
- [ ] Read DOLI child labor section and draft work permit plain-language summary
- [ ] Confirm which programs are active for Summer 2026 vs. year-round

### Maternal Health teams
- [ ] Obtain free Census API key at https://api.census.gov/data/key_signup.html (takes ~24 hours; do this before Friday)
- [ ] Identify correct ACS table codes: B27001 (health insurance), C17001 (poverty), B01001 (age/sex)
- [ ] Download VDH maternal health data sample and inspect column structure
- [ ] Download Kids Count Virginia CSV sample and inspect column structure
- [ ] Confirm which year's data is most current for each source

---

## Content Accuracy Checks (All Teams)

- [ ] Work permit guidance: have someone with legal literacy review before demoing
- [ ] Program eligibility claims: link to official source; do not assert eligibility directly
- [ ] Maternal health statistics: verify each number against named source before displaying
- [ ] Any "Richmond-specific" claim: confirm it refers to City of Richmond, not Richmond metro or MSA

---

## Post-Demo Verification

- [ ] Update `evidence_log.md` with all confirmed sources, URLs, and access dates
- [ ] Update `02_data/source_inventory.csv` with verified access methods and field names
- [ ] Document any inaccuracies discovered during testing and how they were corrected
