# evidence_grounded_answering

Purpose: Answer user questions using only content actually present in this repository corpus, with explicit grounding and uncertainty marking.

## When To Use
- Any time a factual claim about Richmond programs, data, or services is being made
- When a user asks: "Does X exist?" "Is Y available?" "What does the City do about Z?"
- When an agent is about to state something it cannot directly verify from files it has read
- Before asserting that a dataset, program, service, or policy exists
- Before claiming a specific statistic (e.g., "750 youth served by Youth Works RVA" or "D3=1 data readiness score")

## Inputs
- User question
- Files read in current context
- Optional: `evidence_log.md` for verified claims

## Outputs
- Answer grounded in specific file content
- Inline citations for each substantive claim
- Explicit uncertainty markers for unverified statements
- "Not found" statements when information is absent

## Process

### Step 1 — Establish What Has Been Read

Before answering, state (internally or explicitly) which files have been read. Only make claims from those files. Do not interpolate from general knowledge about youth employment or maternal health.

### Step 2 — Classify Each Claim

For every substantive claim in your answer, classify it:

| Status | Meaning | Marker |
|--------|---------|--------|
| `Confirmed` | Present in a source file AND verified in `evidence_log.md` | No marker needed; cite source |
| `Stated in corpus` | Present in a research file but not independently verified | `(per [filename])` |
| `Uncertain` | Implied or summarized but not directly stated in a file read | `[Uncertain: implied by X but not stated directly]` |
| `Not found` | Not present in any file read | `[Not found in files read]` |
| `Requires reading` | Likely in a specific file that has not been read | `[Requires reading: filename]` |

### Step 3 — Check the Evidence Log

For claims about:
- Specific program details (Youth Works RVA capacity, application deadlines)
- DOLI work permit requirements and sequencing
- GRTC Zero Fare policy and funding status
- VDH data availability at city/locality level
- KIDS COUNT data access and update cadence
- Any processing timelines or program eligibility ages

Cross-check `evidence_log.md`. If the claim has a `Confirmed` entry, cite it with high confidence. If the claim is not in the log, mark it `[Stated in corpus: not independently verified]`.

### Step 4 — Formulate the Answer

Structure:
1. Direct answer to the question
2. Supporting evidence with citations
3. Explicit uncertainty statements
4. What is NOT covered (to set expectations)

### Step 5 — Apply the Anti-Fabrication Check

Before finalizing the answer, run this check:

- Does every named government program (Youth Works RVA, DOLI, VDH, GRTC) actually appear in a file I have read?
- Does every dataset I mentioned (ACS, KIDS COUNT, GTFS) actually appear in D section files or `02_data/`?
- Does every statistic I cited (750 youth, D3=1 score, Zero Fare funding through FY26) appear in a research file I read?
- Am I inventing specificity (exact percentages, exact dates, exact eligibility ages) not present in the source?

If any check fails → remove or mark the claim as `[Unverified]`.

### Step 6 — State Scope Limits

At the end of the answer, state:
- What files were used to answer this question
- What topics the answer does NOT cover because relevant files were not read

## Required Language

When information is absent, use:
- "This repository does not contain that information."
- "I cannot verify that from the files I have read in this session."
- "That would require reading [specific file] which I have not yet loaded."
- "[Unverified]: this appears in a summary but I have not read the source file."

Do NOT use:
- "Likely..."  (without a citation)
- "Generally..." (as a hedge for an ungrounded claim)
- "It is common for cities to..." (implies external knowledge not in corpus)
- "I believe..." (implies opinion substituting for evidence)
- "Richmond probably has..." (speculates without grounding)

## Special Cautions for Thriving Families Topics

**Youth employment:** Do NOT invent program names, eligibility ages, application windows, or employer directories. These must come from D section files or C section files.

**Maternal health:** Do NOT state specific health statistics (mortality rates, uninsured rates) unless they appear in D2, D3, or D4 files you have read. Maternal health statistics are sensitive and must be cited precisely.

**DOLI work permits:** The permit sequencing (offer-first, permit-second, work-third) is a specific legal requirement. Only state it if you have read D1.

**GRTC Zero Fare:** The funding cliff (FY2026 funding, potential post-2026 uncertainty) is a specific claim. Only state it if you have read D5 or A1.

## Example

**Question:** "Does Richmond have a youth jobs portal?"

**Grounded answer:**

No centralized youth jobs portal exists in Richmond as of the problem statement (per `research/A1_problem_landscape_youth_employment.md`). Youth Works RVA maintains its own application portal, RPS has a work-based learning page, and nonprofits maintain separate pages — but there is no unified discovery marketplace. This fragmentation is documented as a core problem (per `research/A1`; the D3=1 data readiness score reflects the absence of a compiled program directory).

[Requires reading: `research/C1_services_youth_workforce_programs.md` for a current inventory of all programs and their digital front doors.]

*Files read for this answer: A1*
*Not covered: C1 (current program details), B1 (teen user experience of the gap)*

## Anti-Patterns

- Never state a City program exists without a source file citation
- Never quote a statistic (capacity numbers, score values, funding years) without a source
- Never say "Richmond has X program" based only on index.json summaries
- Never blend confirmed and uncertain claims in the same sentence without differentiation
- Never state medical or health statistics without citing the specific D2 or D3 file
