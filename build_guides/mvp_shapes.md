> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# MVP Shapes - Thriving Families

---

## Shape A — Youth Employment Pathway Guide
### Best for
Teams with content research and UX strength. Does not require data engineering.

### Problem addressed
Youth Employment (Statement 1)

### Inputs
- Curated list of Richmond youth employment programs (team-created; 8–15 entries)
- Virginia work permit plain-language summary (team-created from DOLI)
- Document preparation checklist (team-created)
- Program eligibility and application window data (researched from program websites)

### Demo
Teen selects age and interest area → tool shows relevant programs, required documents, and next steps — all with links to official sources.

### Notes
This is the most weekend-feasible shape for a D3=1 problem. Content curation is the build. Technology is the delivery layer.

---

## Shape B — Job Readiness Checklist
### Best for
Teams with limited data access; small teams; teams strongest in content and frontend.

### Problem addressed
Youth Employment (Statement 1) — preparation dimension

### Inputs
- Virginia work permit requirements (DOLI)
- Standard document list for teen first employment
- Basic resume/interview preparation tips from public sources

### Demo
Interactive checklist that tracks what a teen has gathered and what remains. Each item links to an official source or plain-language explanation.

### Notes
Smallest and fastest of all shapes. Can be built in 8–10 hours. Strong demo because it directly solves a clear pain point (teens don't know what they need).

---

## Shape C — Employer-Youth Connector
### Best for
Teams with research capacity to curate an employer/program list and a developer who can build filter/search UI.

### Problem addressed
Youth Employment (Statement 1) — discovery dimension; employer friction

### Inputs
- Curated list of youth-friendly programs and employers (team-created; 10–20 entries)
- Plain-language employer obligations summary (DOLI)
- GRTC transit context for locations (optional; GTFS-based)

### Demo
Teen filters by age, location, and interest → sees matching programs with bus access note → employer side shows what hiring a teen requires.

### Notes
Dual-audience (teen and employer) makes this more complex to scope. Consider focusing on one side for the demo. Do not build a formal matching system.

---

## Shape D — Maternal Health Data Aggregator
### Best for
Teams with data engineering skills; able to verify API access before Saturday.

### Problem addressed
Maternal Health Data Coordination (Statement 2)

### Inputs
- ACS (Census API — free key required; table codes need research)
- VDH maternal health data (download — format needs verification)
- Kids Count Virginia (CSV download)

### Demo
Researcher opens dashboard → sees 6–8 maternal health indicators for Richmond with source, date, and definition. No manual compilation needed.

### Notes
Spend Friday evening verifying data access before committing to this shape. If ACS API key takes more than 30 minutes, switch to CSV downloads. Do not make clinical claims.

---

## Shape E — Shared Indicator Dictionary + Dashboard
### Best for
Teams with content research and frontend skills; data skills helpful but not required.

### Problem addressed
Maternal Health Data Coordination (Statement 2) — definitions and coordination dimension

### Inputs
- Curated set of 8–12 maternal health indicators with official definitions
- Source links (VDH, CDC, ACS, Kids Count)
- Methodology notes and caveats per indicator

### Demo
Researcher searches "infant mortality" → sees standard definition, Richmond value with source and vintage, link to official source, and caveats about data completeness.

### Notes
This is the most tractable maternal health shape if live data access proves difficult. The indicator dictionary alone is a valuable, durable artifact. Can be implemented as a searchable static site.
