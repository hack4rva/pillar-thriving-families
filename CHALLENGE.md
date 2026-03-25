# Thriving Families — Hackathon Challenge

This file defines the two practical problem statements for this pillar and the top-rated blue sky vision. Read this before reading anything else in the repository.

---

## The Two Problems You're Solving

### Problem 1: Expanding Youth Employment Pathways

**Score: 23/32 — Needs work**
**⚠ Critical data gap: D3=1 — lowest data readiness score across all 12 targeted statements in this hackathon. No datasets are currently linked. Teams must curate content manually or scope to guidance without live data.**

**Statement:**
How might we use technology to improve how Richmond youth find, prepare for, and access early employment opportunities — including summer jobs, internships, and job-shadowing experiences — so that the path from interest to employment feels clear, supported, and achievable, while respecting youth labor laws, parental consent requirements, staffing capacity, and transportation barriers?

**Why this problem matters:**
Early work experience helps Richmond youth build skills and long-term workforce attachment. For youth without strong adult support networks, these opportunities provide critical exposure. The process of securing a first job is fragmented and confusing. Employers also face barriers hiring youth — uncertainty about labor rules and no streamlined connection to prepared candidates. Both sides of the match are stuck.

**Build toward:**
- Youth employment pathway guide — step-by-step content + guided flow for first-time job seekers
- Job readiness checklist and document preparation helper for teens (what documents, what forms, what to expect)
- Employer-youth connector — lightweight discovery or matching between willing employers and prepared youth
- Transportation-aware program finder — workforce programs overlaid with GRTC transit routes

**Key constraints:**
- Respect state youth labor laws and parental consent requirements
- Do not store personal information about minors — FERPA and COPPA apply
- Do not make employment determinations or eligibility rulings
- Complement existing programs (Office of Community Wealth Building) — do not duplicate them
- Transportation access is a real barrier — factor it into any solution claiming citywide reach

**Data gaps — these must be resolved before building (or your scope must exclude them):**
- No list of current youth employment programs with eligibility, application windows, and locations exists in this repository
- No employer directory of businesses willing to hire youth exists
- No Virginia youth labor law plain-language summary is linked
- No GRTC transit data is linked for transportation overlay
- Teams choosing this problem must curate content manually or scope to guidance-only (no live data layer)

---

### Problem 2: Maternal Health Data Coordination

**Score: 23/32 — Needs work**
**⚠ Data source URLs for the four named datasets have not been verified. Teams must confirm access before building.**

**Statement:**
How might we use technology to reduce fragmented and duplicative maternal health data analysis across agencies and nonprofit organizations so that Richmond's maternal health ecosystem can operate from unified, consistent metrics while respecting data-sharing limitations and staffing constraints?

**Why this problem matters:**
Maternal health stakeholders across Richmond independently compile the same datasets — Virginia Department of Health (VDH) maternal health data, ACS population data, Kids Count Virginia indicators, and school/insurance coverage data. This produces duplicated effort, inconsistent metrics, and fragmented reporting. Reduced federal funding and increasing pressure to demonstrate measurable outcomes make alignment around shared indicators urgent.

**Build toward:**
- Maternal health data aggregator — unified view of public datasets in one place
- Shared indicator dashboard for maternal health stakeholders — common metrics, updated from public sources
- Data source navigator — tells organizations what data is available, where to find it, what format it's in
- Grant application data kit — pre-compiled, standardized data package organizations can download and reuse

**Key constraints:**
- Do not make clinical recommendations or patient-level health claims
- Operate within legal and policy limits around health data sharing — this tool is for researchers and organizations, not patients
- Support, do not replace, expert interpretation of health data
- Remain cost-effective and sustainable — this must work without ongoing staff commitment to maintain custom data pipelines

**Data sources to verify before building:**
- VDH maternal health portal — URL not yet confirmed in this repository
- Census ACS tables — access method (API, CSV) not specified
- Kids Count Virginia — URL and data format not confirmed
- VDOE data — URL and access method not confirmed
- Teams must verify each source exists and is accessible before building a pipeline that depends on it

---

## The Blue Sky Vision

### Connecting Youth and Employers Across the City — 21/27 — Strong ★ Recommended

**Statement:**
How might we use technology to make it easier for Richmond youth to discover employment opportunities and for local employers to find prepared teen candidates — so that the match between willing workers and willing employers happens more reliably?

**Why this scored well:**
Clear two-sided problem with a natural software shape (matching/discovery). Employer confidence is a real, documented friction point — employers want to hire youth but don't know the rules or how to find candidates. Data challenge: no employer directory exists and must be curated.

**Hackathon path if you're aiming at this vision:**
Scope to discovery and matching guidance — not formal hiring. A weekend team cannot build a full two-sided marketplace, but can build:
- A youth-facing side: "here are employers in Richmond who have expressed interest in hiring teens, here's what they look for, here's how to apply"
- An employer-facing side: "here's what hiring a Richmond youth requires, here's how to connect with prepared candidates through these programs"

Both sides require content curation. Partner with the Office of Community Wealth Building or a workforce nonprofit if possible — they have the relationships that make this real.

---

## How Your Solution Will Be Judged (Pillar Award)

The Pillar Award uses the following weights. For full category definitions and scoring anchors, see [`/RUBRIC.md`](../../RUBRIC.md) at the hackathon root.

| Category | Weight | What judges are asking |
|----------|--------|------------------------|
| **Impact** | **5** | Does this directly address one of the two problem statements above? |
| **User Value** | 4 | Is there a specific, real user? Does the prototype improve their experience? |
| **Feasibility** | 3 | Could this be piloted by a workforce org or health coalition within a year? |
| **Innovation** | 3 | Does the team bring fresh thinking to youth employment or health data coordination? |
| **Execution** | 3 | Does a working demo exist? Is the flow coherent? |
| **Equity** | 3 | Does the solution reach youth without strong adult support networks, or under-resourced health orgs? |

**Score formula:** Sum of (category score 1–5 × weight). Maximum 105.

**Tiebreaker:** User Value score.

**What wins here:** A prototype that makes the path to first employment clearer for Richmond youth, or that reduces duplicated data work for maternal health organizations, with real content and a working demo.

**What loses here:** Tools making employment or clinical determinations, solutions storing personal information about minors, or projects building on data sources that have not been confirmed as accessible.
