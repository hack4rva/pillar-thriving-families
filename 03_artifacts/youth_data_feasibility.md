> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Youth Employment Data Feasibility Analysis

## The D3=1 Problem

The Youth Employment problem statement received a D3 (Data Readiness) score of 1 out of 4 — the lowest score across all 12 targeted statements evaluated in this hackathon cycle.

This is the most important constraint your team needs to understand before scoping your MVP.

---

## What D3=1 Means in Practice

D3=1 means: **no usable structured dataset exists and none can be reliably obtained in the time available.**

Specifically, the rubric evaluation identified these missing datasets:
1. A list of current Richmond youth employment programs (name, org, age eligibility, application window, location) — **does not exist in a structured, public form**
2. An employer directory of businesses willing to hire youth — **does not exist**
3. A plain-language summary of Virginia youth labor laws — **exists as legal text only; plain-language version must be created**
4. GRTC transit routes overlaid with employer/program locations — **GRTC data exists in GTFS format; the overlay does not exist**
5. A workforce development section in Richmond's open data catalog — **does not exist**

---

## What Actually Exists (Verified or High-Confidence)

| Source | What Exists | Format | Confidence |
|--------|-------------|--------|------------|
| Virginia DOLI | Youth labor law text (Code of Virginia) | Web/PDF | High |
| OCWB rva.gov | Program descriptions (text, unstructured) | Web | Medium |
| Girls For A Change | Program pages | Web | Medium |
| Boys & Girls Club | Program pages | Web | Medium |
| GRTC | GTFS route and stop data | GTFS (zip) | High — direct download (no auth): https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip (corrected 2026-03-18) |
| Virginia Career Works | State workforce program descriptions | Web | High |

---

## What Needs to Be Created

If your team chooses Youth Employment, you will need to **create** most of your content assets. This is normal for civic hackathons with low data readiness. Here is what you need and how to approach it:

### 1. Program Directory (critical)
- **What:** A list of 8–15 Richmond youth employment programs with: name, org, age eligibility, application period, location, and website link
- **How:** Manual research from OCWB, Girls For A Change, Boys & Girls Club, Richmond Ed Fund, and any other orgs you identify
- **Time estimate:** 2–3 hours to compile; 1–2 hours to verify
- **Output format:** Simple JSON or CSV; 8–15 rows is sufficient for a demo
- **Risk:** Some programs may be seasonal or inactive; label everything as "verify directly with the program"

### 2. Work Permit Plain-Language Summary (important)
- **What:** A clear, teen-friendly explanation of how to get a Virginia work permit if you are under 18
- **How:** Read Virginia Code § 40.1-80 through § 40.1-101 (child labor); DOLI website; distill into 4–6 plain steps
- **Time estimate:** 1–2 hours to draft; 30 minutes to review for accuracy
- **Output format:** Markdown or structured content; link to official DOLI form, do not reproduce it
- **Risk:** Must be accurate; do not paraphrase in ways that alter meaning; label as "based on DOLI guidance, verify with DOLI"

### 3. Document Checklist (helpful)
- **What:** A list of documents a teen typically needs to gather before applying for a first job
- **How:** Research from DOLI, standard employer requirements, work permit process
- **Time estimate:** 1 hour
- **Output format:** Checklist items with explanation; no user data storage
- **Risk:** Low — this is generic guidance; link to official sources

### 4. Transit Context (optional but high-value)
- **What:** For each program location, note which GRTC bus lines are nearby
- **How:** Download GRTC GTFS; map program addresses to nearest stops; identify relevant routes. Direct download URL (no authentication required): https://www.ridegrtc.com/wp-content/uploads/2025/02/gtfs.zip (corrected 2026-03-18)
- **Time estimate:** 2–4 hours depending on team data skills
- **Output format:** Add "nearest bus stop" and "routes" fields to program directory
- **Risk:** GTFS data requires parsing skills; this is a stretch goal, not a core requirement

---

## The Weekend-Viable Strategy

Do not wait for data that does not exist. Do not build infrastructure to collect data in real time.

**The right approach:**
1. Spend Friday evening and Saturday morning curating your content assets (program list, work permit guide, document checklist)
2. Build your UI and flow around the curated content
3. Use the curated content as your data layer — a JSON file is sufficient
4. Label all content clearly with source and "verify directly with the program for current availability"
5. Build the transit overlay only if you have a data engineer with GTFS experience and time to spare

**What a compelling demo looks like without live data:**
A teen selects "I am 16 years old, I live in the East End, I'm interested in retail or food service" → the tool shows 3–4 matching programs with age eligibility confirmed, a plain-language work permit checklist, and transit context for each location. Every item links to an official source. The demo is believable, useful, and honest about its limits.

---

## What to Avoid

- Building a job board that pulls from Indeed or LinkedIn — this is not a Richmond youth employment tool
- Claiming real-time availability data — you do not have it
- Storing any personal information about teens — this is a hard constraint
- Building an employer certification or vetting system — too complex, legally fraught
- Waiting for OCWB to provide a dataset — there is no structured dataset to provide

---

## If You Choose This Problem, Your First 4 Hours Are Data Curation

Before you write a single line of code:
1. Identify 8–12 Richmond youth employment programs from public websites
2. Record: name, org, age eligibility, application window, location, contact/URL
3. Summarize Virginia work permit requirements in plain language (4–6 steps)
4. Build a document checklist (5–8 items with plain descriptions)
5. Save everything as a JSON or CSV file — this is your data layer

This is not a shortcut. This is the right approach for a D3=1 problem.
