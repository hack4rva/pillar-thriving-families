# Research Corpus Guide

**Thriving Families Pillar — Richmond Civic Hackathon**

This file is the canonical orientation document for both human readers and AI agents using this research corpus. Read it before diving into individual reports.

---

## What This Corpus Is

This repository contains a structured research corpus on Richmond's Thriving Families problem space — youth employment pathways and maternal health data coordination — organized to support a weekend civic hackathon. It includes:

- **51 deep research reports** generated via Parallel.ai (in `research/`)
- **Evidence-synthesized artifacts** (in `03_artifacts/`)
- **Data source inventory** (in `02_data/`)
- **Build and demo guides** (in `04_build_guides/`)
- **Skills** — executable procedural guides for AI agents (in `skills/`)
- **Templates** — team and project scaffolding (in `99_templates/`)

The corpus covers two targeted problem statements: **Expanding Youth Employment Pathways** (D3=1, data-scarce) and **Maternal Health Data Coordination** (D3=3, data-available). It is grounded in publicly verifiable claims about Richmond. It does not contain invented data, unverified program descriptions, or fabricated citations.

---

## Canonical Source of Truth

| Priority | File | What It Contains |
|----------|------|-----------------|
| 1 (highest) | `research/[SECTION][N]_*.md` | Primary research reports — authoritative content |
| 2 | `evidence_log.md` (root) | Verified claims with official source status |
| 3 | `research_notes.md` (root) | Research hub with promoted findings |
| 4 | `03_artifacts/*.md` | Synthesized artifacts (journeys, recommendations, feasibility) |
| 5 (lowest) | Index and manifest files | Navigation aids — not authoritative for claims |

**Rule:** Navigation aids (README, index.json, manifest.json, CORPUS_GUIDE.md) reduce search scope. They are not substitutes for reading original reports. Before making substantive claims, read the source report.

---

## How the Corpus Is Organized

### Top-Level Directories

```
research/         ← 51 deep research files (the core corpus)
03_artifacts/     ← synthesized artifacts (user journeys, prototype recommendations)
02_data/          ← data source inventory and index
04_build_guides/  ← MVP shapes, architectures, demo advice
00_core/          ← pillar overview and MAP alignment
01_problem_space/ ← problem statements (scored)
skills/           ← agent skill definitions
99_templates/     ← team and project templates
evidence_log.md   ← root-level verified claims tracker
research_notes.md ← root-level research hub
```

### Research Section Structure

The `research/` directory is organized into labeled sections:

| Section | Topic | Files |
|---------|-------|-------|
| `00–01` | Context & Framing | 2 files |
| `90–93` | Cross-Cutting Analysis | 4 files |
| `A` | Problem Landscape | A1–A5 |
| `B` | Users & Stakeholders | B1–B5 |
| `C` | Services & Programs | C1–C5 |
| `D` | Data Sources | D1–D5 |
| `E` | Prior Art & Benchmarks | E1–E5 |
| `F` | Opportunity Spaces | F1–F5 |
| `G` | Risks & Guardrails | G1–G5 |
| `H` | MVP Shape & Constraints | H1–H5 |
| `I` | Demo Strategy | I1–I5 |

---

## How to Navigate the Corpus

### Start With Navigation Artifacts (Always)

**Before reading any research report, use navigation files to narrow scope:**

1. **`manifest.json`** (root) — machine-readable index of all significant files with summaries and tags
2. **`research/index.json`** — structured metadata for all 51 research files (id, section, title, summary, key_terms)
3. **`research/INDEX.md`** — human-readable table of contents for the research directory
4. **`README.md`** (root) — decision phases and overall repo map

### Navigation Decision Tree

```
User question received
        ↓
Is it about the hackathon process?
  YES → README.md, QUICKSTART.md, 04_build_guides/
  NO ↓
Is it about a specific problem domain?
  Youth employment → research/A1, A4, B1, D1, D5, F2, H2
  Maternal health data → research/A2, A5, B3, D2, D3, D4, F3, H3
  Both / unsure → read 00_pillar_summary_context first
        ↓
Narrow to section using research/index.json
        ↓
Read original .md files for claims
        ↓
Verify against evidence_log.md if needed
```

### Question-to-Section Mapping

| User Question Type | Start Here |
|-------------------|-----------|
| What problems exist? | `A` section (A1–A5) |
| Who are the users? | `B` section (B1–B5) |
| What services exist already? | `C` section (C1–C5) |
| What data is available? | `D` section (D1–D5), `02_data/` |
| What has been built elsewhere? | `E` section (E1–E5) |
| What should we build? | `F` section (F1–F5) |
| What could go wrong? | `G` section (G1–G5) |
| Is this feasible in a weekend? | `H` section (H1–H5) |
| How do we demo this? | `I` section (I1–I5) |
| What datasets are available? | `D1`, `D2`, `D3`, `D4`, `D5`, `02_data/source_inventory.csv` |
| What is the executive summary? | `research_notes.md`, `research/00_pillar_summary_context.md` |
| Which problem is more buildable? | `research/A3_problem_landscape_compare_statements.md` |
| What are the guardrails? | `research/G5_risks_guardrails.md`, `research/F5_opportunities_do_not_build.md` |

### Problem-Domain-Specific Navigation

**For Youth Employment questions:** prioritize A1, A4, B1, B4, D1, D5, F2, H2, H4
- Start: `research/A1_problem_landscape_youth_employment.md`
- Data: `research/D1_data_youth_labor.md`, `research/D5_data_grtc_transit.md`
- Build: `research/H2_mvp_youth_employment.md`

**For Maternal Health Data questions:** prioritize A2, A5, B3, D2, D3, D4, F3, H3
- Start: `research/A2_problem_landscape_maternal_health_data.md`
- Data: `research/D2_data_vdh_maternal.md`, `research/D3_data_census_acs.md`, `research/D4_data_kids_count.md`
- Build: `research/H3_mvp_maternal_health.md`

---

## How to Use the Metadata Files

### `research/index.json`

A JSON array with one entry per research file. Each entry has:
- `id` — file basename (e.g., `A1_problem_landscape_youth_employment`)
- `section` — section label (e.g., `A`, `B`, `cross-cutting`)
- `title` — display title
- `summary` — 1–2 sentence grounded summary
- `key_terms` — 6 relevant terms for keyword search

**Use it to:** find which files are relevant before reading them. Do not answer questions from summaries alone — read the source `.md` file.

### `manifest.json`

A comprehensive machine-readable index of all significant files in the repository. Each entry includes:
- `id`, `path`, `type`, `title`, `summary`
- `pillar`, `tags`, `recommended_audience`
- `read_after` — what to read first
- `source_of_truth` — whether this file is authoritative

**Use it to:** build a retrieval index, understand the full scope of the corpus, or identify which file type to use for a given purpose.

### `evidence_log.md` (root)

A log of verified and likely claims about Richmond's Thriving Families problem space. Status values: `Confirmed`, `Likely but Unverified`, `Missing`.

**Use it to:** check whether a specific factual claim has been verified. Do not invent claims that are not in this log.

---

## How AI Agents Should Use This Corpus

### Required Behavior

1. **Always read navigation artifacts before raw reports.** Start with `research/index.json` or `manifest.json` to identify relevant files. Do not dive into arbitrary `.md` files without knowing their scope.

2. **Read original reports before making substantive claims.** The summaries in index files are useful for navigation, not for citation. If a question requires a specific fact, find it in the source `.md` file.

3. **Scope before answering.** Identify the relevant section(s) first. A question about youth employment data belongs to sections `D` and `A1`. A question about demo strategy belongs to section `I`.

4. **Acknowledge when files have not been read.** If a report appears relevant but has not been read in the current context, say so rather than guessing from summaries.

5. **Cite the source file.** When presenting findings, reference the file they came from (e.g., "Per `research/A1_problem_landscape_youth_employment.md`...").

6. **Distinguish navigation files from source-of-truth files.** `manifest.json`, `README.md`, `research/INDEX.md`, and `index.json` are navigation aids. They are not authoritative for factual claims.

7. **Mark uncertainty explicitly.** If a claim cannot be verified from the files that have been read, use: `[Unverified]` or `[Requires reading: filename]`.

### How to Answer Cross-Report Questions

When a question requires synthesis across multiple reports:
1. Use `research/index.json` to identify all potentially relevant files
2. Read the summaries, then decide which reports need full reading
3. Read the source files
4. Synthesize from source content, citing each report separately
5. Note any tensions or contradictions between reports
6. Do not blend claims from different sections without acknowledging the synthesis

### When to Read Additional Files

You MUST read additional files before answering if:
- The question involves a specific dataset or data format → read D section
- The question involves a specific user persona → read B section
- The question requires a factual claim about Richmond programs → check `evidence_log.md`
- The answer requires citing prior art → read E section
- The question is about risk or guardrails → read G section
- The question involves comparing the two problem statements → read A3

---

## What This Corpus Does NOT Contain

- Legal advice or eligibility determinations
- Official City positions or policy commitments
- Private data about minors or patients
- Authoritative medical or clinical guidance
- Verified program availability (programs change; always encourage users to verify current status)
- A compiled dataset of Richmond youth employment programs (D3=1 — this gap is documented but not filled)

When information is absent, say: "This repository does not contain that information."

---

## Recommended Reading Order for Common Scenarios

### New team at hackathon start
1. `README.md` → `QUICKSTART.md` → `00_core/00_pillar_overview.md`
2. `01_problem_space/02_targeted_problem_statements.md`
3. `research_notes.md` (executive brief / research hub)
4. `04_build_guides/01_mvp_shapes.md`

### Team choosing between Youth Employment and Maternal Health
1. `research/A3_problem_landscape_compare_statements.md`
2. `research/F1_opportunities_ranked.md`
3. `research/H1_mvp_48hr_framework.md`
4. `01_problem_space/02_targeted_problem_statements.md`

### Team deep-diving on Youth Employment
1. `research/A1_problem_landscape_youth_employment.md`
2. `research/D1_data_youth_labor.md`
3. `research/D5_data_grtc_transit.md`
4. `research/H2_mvp_youth_employment.md`
5. `research/H4_mvp_data_constraints.md`

### Team deep-diving on Maternal Health Data
1. `research/A2_problem_landscape_maternal_health_data.md`
2. `research/D2_data_vdh_maternal.md`
3. `research/D3_data_census_acs.md`
4. `research/D4_data_kids_count.md`
5. `research/H3_mvp_maternal_health.md`

### Team deep-diving on data availability
1. `02_data/source_inventory.csv` and `02_data/00_index.md`
2. `research/D1_data_youth_labor.md`
3. `research/D2_data_vdh_maternal.md`
4. `research/D5_data_grtc_transit.md`
5. `evidence_log.md`

### Agent answering research questions
1. `research/index.json` → identify relevant section
2. `research/INDEX.md` → narrow to specific files
3. Source `.md` files → read for claims
4. `evidence_log.md` → verify specific facts

---

## File Naming Conventions

Research files follow the pattern: `[SECTION][NUMBER]_[TOPIC_SLUG].md`

Examples:
- `A1_problem_landscape_youth_employment.md` — Section A, file 1, topic: youth employment problem
- `G5_risks_guardrails.md` — Section G, file 5, topic: guardrails
- `90_top_10_research_questions.md` — Cross-cutting file 90

Sections run A through I. Numbers within sections run 1–5. Cross-cutting files use 90–93. Context files use 00–01.

---

## See Also

- `AGENTS.md` — Hackbot agent specification and research corpus navigation instructions
- `MAINTENANCE.md` — How to add, update, and synchronize reports and metadata
- `manifest.json` — Machine-readable index of all significant files
- `research/index.json` — Machine-readable index of all research reports
- `research/INDEX.md` — Human-readable table of contents for research directory
