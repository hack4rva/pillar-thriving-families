> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../../docs/methodology.md) for details.

# research_corpus_navigation

Purpose: Map a user question to the correct section and specific research reports before attempting to answer.

## When To Use
- A user asks any research question about Richmond's Thriving Families problem space
- A user asks about youth employment, maternal health data, DOLI compliance, GRTC transit, or related topics
- A user asks what reports to read
- An agent needs to determine which files are relevant before answering

## Inputs
- User question or information need (natural language)

## Outputs
- Identified section(s) from the research corpus
- List of specific files to read (in recommended order)
- Brief explanation of why each file is relevant
- Any files that must be read before answering (prerequisites)

## Process

### Step 1 — Load Navigation Artifacts

Before looking at any research file, load:
1. `research/index.json` — scan all summaries and key_terms
2. If the corpus is unfamiliar: read `CORPUS_GUIDE.md` first

Do NOT skip this step and dive directly into research files.

### Step 2 — Classify the Question

Determine which category the user question falls into:

| Question Category | Relevant Sections |
|------------------|------------------|
| "What problems exist in this space?" | Section A (A1–A5) |
| "Who are the users or stakeholders?" | Section B (B1–B5) |
| "What services or programs exist?" | Section C (C1–C5) |
| "What public data is available?" | Section D (D1–D5), `02_data/` |
| "What has been built elsewhere?" | Section E (E1–E5) |
| "What should we build?" | Section F (F1–F5) |
| "What could go wrong?" | Section G (G1–G5) |
| "Is this feasible for a weekend?" | Section H (H1–H5) |
| "How should we demo this?" | Section I (I1–I5) |
| "What is the overall picture?" | `research_notes.md`, `research/00_pillar_summary_context.md` |
| "What datasets or APIs are mentioned?" | D1–D5, `02_data/source_inventory.csv` |
| "Youth employment specific" | A1, A4, B1, B4, D1, D5, F2, H2, H4 |
| "Maternal health data specific" | A2, A5, B3, D2, D3, D4, F3, H3 |
| "Which problem to choose?" | A3, F1, H1 |
| "What not to build?" | F5, G1, G2 |

### Step 3 — Search `research/index.json`

Scan the `key_terms` and `summary` fields for matches to the user's question. Identify:
- High-confidence matches (3+ matching key_terms)
- Medium-confidence matches (1–2 matching key_terms)
- Files worth reading despite no term match (based on section relevance)

### Step 4 — Build a Reading List

Order files by:
1. Direct relevance to the question
2. Section order (earlier sections provide context for later ones)
3. Files mentioned in `CORPUS_GUIDE.md` recommended reading orders

Limit the initial reading list to 5 files maximum. If more are needed after reading, say so.

### Step 5 — Identify Prerequisites

Some questions require reading prerequisite files:
- Any question requiring Richmond context → read `research/00_pillar_summary_context.md` first
- Any question about specific services → read C1 before C2–C5
- Any question about data → read D1 (youth) or D2 (maternal) before other D files
- Any question requiring problem framing → read A1 or A2 before F or H sections
- Any question about GRTC transit → read D5 as a prerequisite for youth employment build questions

Flag prerequisites explicitly.

### Step 6 — Output the Navigation Result

Return:
```
Relevant section(s): [X, Y]
Files to read (in order):
  1. research/[FILE].md — [one-sentence reason why]
  2. research/[FILE].md — [one-sentence reason why]
  3. ...

Prerequisites (read these first if not yet read):
  - research/[FILE].md — [reason]

Files to skip (and why):
  - [Section] — not relevant because [reason]
```

### Step 7 — Confirm Scope Boundaries

After delivering the reading list, state:
- What sections were NOT included and why (to confirm you didn't miss something)
- Whether cross-report synthesis will be needed
- Whether any answer requires verified facts from `evidence_log.md`

## Example

**Question:** "What data can we use to build a Richmond youth jobs navigator?"

**Navigation result:**
```
Relevant sections: D (Data Sources), A (Problem Landscape)

Files to read (in order):
  1. research/D1_data_youth_labor.md — primary source on DOLI work permit data and Virginia child labor law
  2. research/D5_data_grtc_transit.md — GRTC GTFS feed for transit overlay
  3. research/A1_problem_landscape_youth_employment.md — context on what data gaps create the problem
  4. research/H4_mvp_data_constraints.md — how to build when compiled datasets don't exist
  5. 02_data/source_inventory.csv — verified data source list with access details

Prerequisites: none (D1 is the logical starting point)

Files to skip: D2, D3, D4 (maternal health data), B3 (maternal health researcher) — not relevant to youth employment

Verified facts to check: evidence_log.md for confirmed youth employment program sources
```
