> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../../docs/methodology.md) for details.

# cross_report_synthesis

Purpose: Synthesize findings from multiple research reports into a coherent answer while preserving source traceability and acknowledging uncertainty.

## When To Use
- A user asks a question that spans multiple reports or sections
- A team needs a summary of findings across a problem domain (e.g., "everything we know about youth employment barriers")
- An agent needs to answer: "What does the research say about X across all relevant reports?"
- A user asks for a synthesis of risks, opportunities, or data sources
- A user asks for a comparison between youth employment and maternal health approaches

## Inputs
- User question or synthesis goal
- List of relevant report files (from `research_corpus_navigation` skill)
- Access to the source `.md` files

## Outputs
- Synthesized answer with per-claim source citations
- Tensions or contradictions noted explicitly
- Confidence level per claim (confirmed, likely, uncertain)
- List of reports read vs. reports not read
- Identified gaps where synthesis is incomplete

## Process

### Step 1 — Load Navigation Context

Before synthesizing, confirm you have run `research_corpus_navigation` or equivalent to identify which files are relevant. Do not synthesize from random file selections.

### Step 2 — Read Source Files Fully

For each file in the reading list:
1. Read the full `.md` file (not just summaries or frontmatter)
2. Note specific claims, data points, named entities, and source citations
3. Note the confidence level of each claim: does the report cite a primary source, or is it a secondary synthesis?

Do NOT synthesize from index summaries alone. Summaries are navigation aids, not authoritative content.

### Step 3 — Build a Claim Map

For each substantive claim you plan to include:

```
Claim: [statement]
Source: [filename, section heading if helpful]
Confidence: confirmed | likely | uncertain
Primary source: [URL or citation if available in the report]
Conflicts with: [other report + how it conflicts, if applicable]
```

### Step 4 — Identify Tensions and Gaps

Before writing the synthesis, explicitly check:
- Do any reports contradict each other? (If so, note both positions and their sources)
- Are there claims that appear in one report but are absent from others where you would expect them?
- Are there questions that the reports together still do not answer?

Flag gaps with: `[Gap: no report in this corpus addresses X]`

### Step 5 — Write the Synthesis

Structure:
1. **Scope**: which files were read, which were not
2. **Main findings**: 3–7 bullet points with inline citations
3. **Tensions**: any conflicting information and its sources
4. **Gaps**: what the corpus does not cover
5. **Confidence summary**: overall confidence in the synthesis

### Citation Format

Use inline citations:
- `(per research/A1_problem_landscape_youth_employment.md)`
- `(per evidence_log.md, Confirmed section)`
- `[Unverified: not found in files read]`
- `[Uncertain: mentioned in summary but not verified in source]`

Never blend claims from different sources into a single uncited sentence.

### Step 6 — State What Was NOT Read

Always end the synthesis with:

```
Files read for this synthesis:
  - research/[FILE].md
  - research/[FILE].md

Files not read (possibly relevant):
  - research/[FILE].md — reason it may contain relevant information
```

This allows the user or a future agent to know the synthesis is incomplete if additional files exist.

## Anti-Patterns to Avoid

- **Never** synthesize from index.json summaries alone
- **Never** blend claims from different reports without attribution
- **Never** omit tensions or contradictions to make the answer cleaner
- **Never** claim the synthesis is complete if relevant unread files exist
- **Never** invent figures or statistics not present in the source files
- **Never** combine youth employment and maternal health findings without clearly labeling which domain each claim belongs to

## Example Output Structure

```
**Synthesis: Youth Employment Data Availability for a Richmond Jobs Navigator**

Files read: A1, D1, D5, H4, 02_data/source_inventory.csv
Files not read (possibly relevant): D2 (VDH maternal health data — not relevant), C1 (program details)

**Main Findings**
1. No compiled dataset of Richmond youth employment programs exists as of the problem statement (D3=1) (per research/A1_problem_landscape_youth_employment.md).
2. DOLI work permits are required for 14–15 year-olds and must be obtained AFTER a firm job offer but BEFORE starting work (per research/D1_data_youth_labor.md).
3. GRTC provides a public GTFS feed that can be parsed to show nearest bus stops to job locations (per research/D5_data_grtc_transit.md).
4. Teams can ship a viable MVP using manually curated seed data from YouthWorks RVA, RPS, and nonprofit program pages (per research/H4_mvp_data_constraints.md).

**Tensions**
- A1 notes D3=1 (no compiled dataset) but H4 argues manual curation can substitute within 48 hours — these are compatible but require explicit framing in the demo [Uncertain: specific curation time estimates not verified].

**Gaps**
- [Gap: no report addresses whether GRTC Zero Fare routes will continue beyond FY2026 — teams should note this as a dependency risk]

**Confidence: Moderate** — main findings confirmed; C1 program details not yet read.
```
