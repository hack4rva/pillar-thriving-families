# Post-Event Research Index — Thriving Families

**Pillar:** Thriving Families
**GitHub:** [hack4rva/pillar-thriving-families](https://github.com/hack4rva/pillar-thriving-families)
**Problem Statements:**
- PS1: Youth Employment Pathways — Give Richmond youth one clear place to explore summer jobs, internships, and first-job guidance
- PS2: Maternal Health Data Coordination — Reduce duplicated analysis so Richmond's maternal health ecosystem operates from shared, consistent metrics

**For AI agents:** Read this file to locate any post-event research artifact. Do not list the directory.

---

## Shared Research (Cross-Demo, Per Problem Statement)

| Dir | JTBD | Pain Points | Prior Art |
|-----|:----:|:-----------:|:---------:|
| [`_shared-youth-employment/`](_shared-youth-employment/) | ✅ | ✅ | ✅ |
| [`_shared-maternal-health/`](_shared-maternal-health/) | ✅ | ✅ | ✅ |

These files synthesize the problem statement across all demos in that PS. Read them before reading any per-project file.

---

## Per-Project Research Inventory

| Project | Problem Statement | JTBD | Pain | Prior Art | Solution Ideas |
|---------|------------------|:----:|:----:|:---------:|:--------------:|
| [`first-job-sms-kit/`](first-job-sms-kit/) | PS1: Youth Employment | ✅ | ✅ | — | — |
| [`grant-pack-builder/`](grant-pack-builder/) | PS1: Youth Employment | ✅ | ✅ | — | — |
| [`multi-pillar-ai/`](multi-pillar-ai/) | Multi-pillar | ✅ | ✅ | — | — |
| [`richmond-youth-hub/`](richmond-youth-hub/) | PS1: Youth Employment | ✅ | ✅ | — | — |
| [`rva-people-data/`](rva-people-data/) | PS2: Maternal Health | ✅ | ✅ | — | — |
| [`rva-works/`](rva-works/) | PS1: Youth Employment | ✅ | ✅ | — | — |
| [`stepwise/`](stepwise/) | PS1: Youth Employment | ✅ | ✅ | — | — |
| [`unboxed-rva/`](unboxed-rva/) | PS1: Youth Employment | ✅ | ✅ | — | — |
| [`unknown-corrupted/`](unknown-corrupted/) | Unknown | ✅ | ✅ | — | — |

**Note:** `multi-pillar-ai` spans multiple pillars. `unknown-corrupted` is a corrupted submission with no recoverable content.

---

## Research Answers (`_research-answers/`)

Parallel AI queries that answered the JTBD open questions. Read `QUERY_MAP.md` to see which file answers which question.

| File | Problem Statement | Questions Answered |
|------|------------------|-------------------|
| [`QUERY_MAP.md`](_research-answers/QUERY_MAP.md) | Both | Full map of JTBD questions → query files |
| [`ye_q1_system_data.md`](_research-answers/ye_q1_system_data.md) | PS1 | VAeECS, Youth Works, employer lists, data availability |
| [`ye_q2_equity.md`](_research-answers/ye_q2_equity.md) | PS1 | User needs, equity gaps, integration requirements |
| [`ye_q3_prior_art.md`](_research-answers/ye_q3_prior_art.md) | PS1 | Prior art, comparable programs, integration possibilities |
| [`mh_q1_data.md`](_research-answers/mh_q1_data.md) | PS2 | VDH datasets, data suppression, race/ethnicity schema |
| [`mh_q2_ecosystem.md`](_research-answers/mh_q2_ecosystem.md) | PS2 | Ecosystem actors, user needs, integration requirements |
| [`mh_q3_prior_art.md`](_research-answers/mh_q3_prior_art.md) | PS2 | Prior art, data governance models |

---

## Agent Reading Sequence

```
1. Read this file (INDEX.md) — orient
2. For PS1 context: _shared-youth-employment/jtbd_analysis.md
3. For PS2 context: _shared-maternal-health/jtbd_analysis.md
4. For a specific project: <project>/jtbd_analysis.md → <project>/pain_points.md
5. For answered research questions: _research-answers/QUERY_MAP.md → relevant query file
```
