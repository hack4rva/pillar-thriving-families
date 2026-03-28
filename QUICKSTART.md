> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](docs/methodology.md) for details.

# Quickstart

## Fastest path for teams
1. Read `00_core/00_pillar_overview.md`
2. Read `01_problem_space/02_targeted_problem_statements.md`
3. Read `02_data/00_index.md`
4. Pick one user and one problem
5. Read `04_build_guides/01_mvp_shapes.md`
6. Create your project brief using `99_templates/project_one_pager_template.md`

## Questions to answer before building
- Who is the user (teen, employer, maternal health researcher, community org staff)?
- What problem are they facing?
- What data or documents are you using?
- What can actually be built in a weekend?
- How will a judge understand the value in under 60–90 seconds?

## High-probability project types
- youth employment pathway guide (guided flow from interest to job application)
- job readiness checklist and document prep helper for teens
- employer-youth connector (lightweight discovery, not a hiring platform)
- maternal health data aggregator (unified view of public VDH, Census, Kids Count data)
- workforce program finder (directory + eligibility guidance)

## Critical warning before you start
Youth Employment has a D3=1 data readiness score — the lowest across all 12 statements evaluated this cycle.
There is no pre-existing compiled dataset of Richmond youth employment programs, employer directories, or transit overlays.
Read `03_artifacts/youth_data_feasibility.md` before scoping any data-dependent feature.
The good news: the problem is content-rich and demoable with curated content instead of live data.

## Paths by problem

### Path A — Youth Employment
Your user is a 14–18 year old Richmond teen.
Start with: `01_problem_space/02_targeted_problem_statements.md` (Statement 1)
Best MVP shapes: Shape A (pathway guide), Shape B (readiness checklist)
Key constraint: no data catalog exists; build with curated content
Key risk: avoid storing any personal information about minors

### Path B — Maternal Health Data Coordination
Your user is a Richmond nonprofit researcher or health agency staff member.
Start with: `01_problem_space/02_targeted_problem_statements.md` (Statement 2)
Best MVP shapes: Shape D (data aggregator dashboard), Shape E (shared indicator view)
Key constraint: use only public data (VDH, ACS, Kids Count, VDOE)
Key risk: avoid clinical claims; this is a data coordination tool, not a health guidance tool
