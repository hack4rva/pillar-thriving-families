> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Prototype Recommendations

---

## Problem 1 — Youth Employment Pathways

### Concept A: Youth Employment Pathway Guide

**What it is:** A step-by-step guided flow that takes a Richmond teen from "I want a job" to "I am ready to apply." Covers discovery, preparation, documentation, and application steps. Content-driven; no live data pipeline required.

**User served:** Richmond teens ages 14–18 with no prior work experience, especially those without strong adult support networks.

**48-hour feasibility:** High. Build as a static web app or guided wizard. Curate content from DOLI, OCWB, program websites. No database required. All content is public.

**Data/content:** Virginia youth labor law summary (DOLI); curated list of 8–12 Richmond youth employment programs; work permit overview (link to official form, not a reproduction); basic resume tips.

**Team roles:** Content researcher, UX/frontend developer, product lead.

**Key risk/limitation:** No live data; program listings may go stale. Must clearly label "check the program website for current availability." Do not reproduce official forms — link to them.

**Compelling demo:** A teen selects age 16 → tool shows which programs are available for 16-year-olds, what documents are needed, and what the work permit process looks like in plain language — all with links to official sources.

---

### Concept B: Job Readiness Checklist

**What it is:** A document preparation and readiness checklist that helps a teen understand and gather everything needed before applying: work permit, parental consent, ID, Social Security card, resume basics. Plain-language descriptions of each item.

**User served:** First-time teen job seekers who do not know what they need.

**48-hour feasibility:** Very high. Static content app or interactive checklist. Lowest complexity of all concepts.

**Data/content:** Virginia work permit requirements (DOLI); parental consent process; standard ID document list; basic resume guidance.

**Team roles:** Content researcher, frontend developer.

**Key risk/limitation:** Must link to official DOLI forms and instructions, never reproduce them. Do not store any user input. Do not claim legal authority.

**Compelling demo:** Teen checks off items as they gather them; tool shows progress and links to the next step with an official source.

---

### Concept C: Employer-Youth Connector

**What it is:** Lightweight discovery tool showing Richmond employers and programs that hire youth, with basic labor law guidance for employers. Two-sided: helps teens find opportunities and helps employers understand what youth hiring requires.

**User served:** Teens seeking opportunities and small employers uncertain about youth hiring compliance.

**48-hour feasibility:** Medium. Requires manual curation of employer/program list. No matching algorithm; simple filter by age, location, and opportunity type.

**Data/content:** Curated list of youth-friendly employers and programs (10–20 entries); plain-language summary of Virginia employer obligations when hiring minors; GRTC bus context for employer locations.

**Team roles:** Researcher (data curation), full-stack developer, UX.

**Key risk/limitation:** Scraped or curated employer list goes stale. Must avoid implying any employer has been vetted or approved. No formal matching — advisory only.

**Compelling demo:** Teen filters by "age 16, East End, interested in food service" → sees 3 programs and 2 employers with bus access notes → clicks through to official application pages.

---

## Problem 2 — Maternal Health Data Coordination

### Concept D: Maternal Health Data Aggregator

**What it is:** A dashboard that pulls from VDH, ACS, and Kids Count to display a consistent set of maternal health indicators for Richmond. Removes the need for each organization to independently download and reconcile the same data.

**User served:** Nonprofit researchers and health agency staff who compile maternal health metrics for grants and advocacy.

**48-hour feasibility:** Medium. Requires verifying API access for ACS (free key), locating VDH download, and pulling Kids Count CSV. Build a simple dashboard (Streamlit, Observable, or static HTML). Most time goes to data verification and format normalization.

**Data/content:** ACS (Census API); VDH maternal health data (download); Kids Count Virginia (CSV).

**Team roles:** Data engineer, frontend developer, researcher (data verification).

**Key risk/limitation:** VDH data format may change; ACS table codes require documentation. Must clearly cite source, access date, and methodology. Must not make clinical claims.

**Compelling demo:** Researcher opens dashboard → sees 6 maternal health indicators for Richmond with source, date, and definition — no manual compilation needed.

---

### Concept E: Shared Indicator Dictionary

**What it is:** A structured reference for maternal health indicators: definition, source, table or field name, data vintage, and known caveats. Solves the "we used different numbers" problem by establishing a shared vocabulary.

**User served:** Researchers and staff across multiple Richmond organizations who need to align on definitions before analyzing data.

**48-hour feasibility:** High. Content-driven. Build as a searchable reference page or simple database. Does not require live API access.

**Data/content:** Curated set of 8–12 indicators with definitions from VDH, CDC, ACS, and Kids Count; links to official source pages.

**Team roles:** Researcher, content designer, frontend developer.

**Key risk/limitation:** Indicators must reflect actual source definitions — do not paraphrase in ways that change meaning. Must include source attribution and update date.

**Compelling demo:** Researcher searches "infant mortality" → sees standard definition, Richmond-specific value with source and date, link to VDH table, and known caveats about data completeness.

---

### Concept F: Workforce Program Finder (Cross-cutting)

**What it is:** A directory of Richmond workforce and social support programs relevant to families — youth employment, maternal health navigation, childcare resources, job training. Helps frontline staff at nonprofits and community centers quickly find and refer families.

**User served:** Case managers, nonprofit staff, and community health workers who do intake and referral.

**48-hour feasibility:** Medium. Requires curating a directory from public web sources. Simple filter/search UI.

**Data/content:** Curated list of programs from OCWB, health orgs, community centers, workforce programs. All public web content.

**Team roles:** Researcher (curation), frontend developer.

**Key risk/limitation:** Directory goes stale without maintenance. Must avoid implying program availability without verification. Do not claim eligibility — "check with the program."

**Compelling demo:** Staff enters "pregnant, 17 years old, no income" → sees 4–5 programs with contact info, eligibility notes, and links — with a clear disclaimer to verify directly with each program.
