> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](methodology.md) for details.

# Participant handout

This file is a copy of [`CHALLENGE.md`](../CHALLENGE.md) plus this cover note so you can share one Markdown document. Official judge categories are described in `RUBRIC.md` at the hackathon repository root (the directory that contains `pillar-repos`). The body below mirrors `CHALLENGE.md` in this repository.

---

# Thriving Families: Hackathon Challenge

This file defines the two practical problem statements for this pillar and the top-rated blue sky vision. Read this before reading anything else in the repository.

---

## The Two Problems You're Solving

### Problem 1: Expanding Youth Employment Pathways

**⚠ Critical data gap:** No datasets are currently linked in this repository. Teams must curate content manually or scope to guidance without live data.

**Statement:**
How might we use technology to improve how Richmond youth find, prepare for, and access early employment opportunities, including summer jobs, internships, and job-shadowing experiences, so that the path from interest to employment feels clear, supported, and achievable, while respecting youth labor laws, parental consent requirements, staffing capacity, and transportation barriers?

**Why this problem matters:**
Early work experience helps Richmond youth build skills and long-term workforce attachment. For youth without strong adult support networks, these opportunities provide critical exposure. The process of securing a first job is fragmented and confusing. Employers also face barriers hiring youth: uncertainty about labor rules and no streamlined connection to prepared candidates. Both sides of the match are stuck.

**Build toward:**
- Youth employment pathway guide: step-by-step content + guided flow for first-time job seekers
- Job readiness checklist and document preparation helper for teens (what documents, what forms, what to expect)
- Employer-youth connector: lightweight discovery or matching between willing employers and prepared youth
- Transportation-aware program finder: workforce programs overlaid with GRTC transit routes

**Key constraints:**
- Respect state youth labor laws and parental consent requirements
- Do not store personal information about minors: FERPA and COPPA apply
- Do not make employment determinations or eligibility rulings
- Complement existing programs (Office of Community Wealth Building): do not duplicate them
- Transportation access is a real barrier: factor it into any solution claiming citywide reach

**Data gaps: these must be resolved before building (or your scope must exclude them):**
- No list of current youth employment programs with eligibility, application windows, and locations exists in this repository
- No employer directory of businesses willing to hire youth exists
- No Virginia youth labor law plain-language summary is linked
- No GRTC transit data is linked for transportation overlay
- Teams choosing this problem must curate content manually or scope to guidance-only (no live data layer)

#### Participant guide: connecting to the rubric (if you chose this problem)

The bullets below are **optional prompts for your team**: ways you might explain your project against the six categories in [`RUBRIC.md`](../../RUBRIC.md). **Judges use `RUBRIC.md`**, not this list; they may interpret categories in context.

- **Impact:** You can show how the prototype makes the path from interest to first job clearer for Richmond youth (or employers), without overclaiming coverage you did not build.
- **User Value:** Name a concrete user (e.g. a teen without a strong adult network, a program navigator) and what becomes easier in one weekend demo.
- **Feasibility:** Stay within youth labor law, consent, and **no storage of minors’ personal information**; label curated or mock data honestly.
- **Innovation:** Go beyond a generic job board: e.g. guided steps, document prep, transit-aware discovery, or employer-facing clarity.
- **Execution:** Someone can follow a flow (even with curated content) and understand the next step for the user.
- **Equity and inclusion:** Call out how you account for transportation barriers and teens without strong adult support.

**What often works well for this problem:** A pathway or checklist with real-ish program content, document-prep guidance, lightweight employer-youth discovery, or a transit-aware finder using real GRTC data when you have it.

**What to avoid for this problem:** Employment or eligibility determinations, collecting/storing personal information about minors without a clear, compliant approach, or presenting unverified listings as complete official data.

*Try asking yourself:* Could a 16-year-old in Southside Richmond use this to see what to do next toward a summer job or internship?

---

### Problem 2: Maternal Health Data Coordination

**⚠ Data source URLs for the four named datasets have not been verified. Teams must confirm access before building.**

**Statement:**
How might we use technology to reduce fragmented and duplicative maternal health data analysis across agencies and nonprofit organizations so that Richmond's maternal health ecosystem can operate from unified, consistent metrics while respecting data-sharing limitations and staffing constraints?

**Why this problem matters:**
Maternal health stakeholders across Richmond independently compile the same datasets: Virginia Department of Health (VDH) maternal health data, ACS population data, Kids Count Virginia indicators, and school/insurance coverage data. This produces duplicated effort, inconsistent metrics, and fragmented reporting. Reduced federal funding and increasing pressure to demonstrate measurable outcomes make alignment around shared indicators urgent.

**Build toward:**
- Maternal health data aggregator: unified view of public datasets in one place
- Shared indicator dashboard for maternal health stakeholders: common metrics, updated from public sources
- Data source navigator: tells organizations what data is available, where to find it, what format it's in
- Grant application data kit: pre-compiled, standardized data package organizations can download and reuse

**Key constraints:**
- Do not make clinical recommendations or patient-level health claims
- Operate within legal and policy limits around health data sharing: this tool is for researchers and organizations, not patients
- Support, do not replace, expert interpretation of health data
- Remain cost-effective and sustainable: this must work without ongoing staff commitment to maintain custom data pipelines

**Data sources to verify before building:**
- VDH maternal health portal: URL not yet confirmed in this repository
- Census ACS tables: access method (API, CSV) not specified
- Kids Count Virginia: URL and data format not confirmed
- VDOE data: URL and access method not confirmed
- Teams must verify each source exists and is accessible before building a pipeline that depends on it

#### Participant guide: connecting to the rubric (if you chose this problem)

The bullets below are **optional prompts for your team**: ways you might explain your project against the six categories in [`RUBRIC.md`](../../RUBRIC.md). **Judges use `RUBRIC.md`**, not this list.

- **Impact:** Show how the tool reduces duplicated analysis or aligns metrics for **organizations** working on maternal health: not clinical care for individuals.
- **User Value:** Name a concrete role (e.g. coalition analyst, grant writer) and a task your demo shortens (e.g. finding a metric, exporting a table).
- **Feasibility:** Build only on **verified** public sources; avoid pipelines that depend on URLs or APIs you have not confirmed.
- **Innovation:** A navigator, shared indicator view, or reusable “data kit” can be more compelling than another one-off spreadsheet.
- **Execution:** Someone can pull or compare at least one real metric or see a credible static mock with a clear path to real data.
- **Equity and inclusion:** Tie metrics or narrative to disparities affecting Black mothers and under-resourced organizations when relevant.

**What often works well for this problem:** A data source navigator, a small dashboard from confirmed public data, or a downloadable package of standardized indicators for grants.

**What to avoid for this problem:** Clinical recommendations, patient-level claims, or live dashboards that depend on sources you have not verified.

*Try asking yourself:* Could a maternal health nonprofit analyst open this and reuse a metric instead of rebuilding the same spreadsheet again?

---

## The Blue Sky Vision

### Connecting Youth and Employers Across the City

**Statement:**
How might we use technology to make it easier for Richmond youth to discover employment opportunities and for local employers to find prepared teen candidates, so that the match between willing workers and willing employers happens more reliably?

**Why this fits a weekend build:**
Clear two-sided problem with a natural software shape (matching/discovery). Employer confidence is a real, documented friction point: employers want to hire youth but don't know the rules or how to find candidates. Data challenge: no employer directory exists and must be curated.

**Hackathon path if you're aiming at this vision:**
Scope to discovery and matching guidance: not formal hiring. A weekend team cannot build a full two-sided marketplace, but can build:
- A youth-facing side: "here are employers in Richmond who have expressed interest in hiring teens, here's what they look for, here's how to apply"
- An employer-facing side: "here's what hiring a Richmond youth requires, here's how to connect with prepared candidates through these programs"

Both sides require content curation. Partner with the Office of Community Wealth Building or a workforce nonprofit if possible: they have the relationships that make this real.

**Rubric connection (blue sky):** This vision is closest to **Problem 1 (youth employment pathways)**. Use the Problem 1 participant guide for reflection prompts. If your demo spans youth and another theme, be explicit about which problem statement you are primarily addressing and use the relevant guide(s).

---

## Judges and the rubric

Hackathon judges evaluate prototypes using the shared categories described in [`RUBRIC.md`](../../RUBRIC.md) at the hackathon repository root. That document lists the category names and what judges are asked to consider.

The **Participant guide** sections under each problem above are optional ways to prepare your pitch. They are not official instructions to judges.
