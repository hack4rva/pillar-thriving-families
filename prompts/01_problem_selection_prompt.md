> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Problem Selection Prompt

Use this prompt to help your team choose between the two Thriving Families problem statements.

---

## Prompt for Hackbot or team discussion

We are a team of [N] people with the following skills: [list skills].

We have [time remaining] until Sunday demo.

We are considering the following Thriving Families problems:
1. Expanding Youth Employment Pathways (D3=1, needs content curation)
2. Maternal Health Data Coordination (D3=3, needs data access verification)

Help us choose one. Evaluate each against:
- Our skill set (can we build it?)
- Data tractability (can we get/create the data in time?)
- Demo credibility (can we show something real by Sunday?)
- User clarity (do we understand the user and their pain?)
- Risk (could our tool mislead or harm someone?)

Produce a recommendation with rationale.

---

## Decision criteria (use this table)

| Criterion | Youth Employment | Maternal Health |
|-----------|-----------------|-----------------|
| Data access | Must curate manually (2–3 hrs content work) | Must verify API access (1–2 hrs setup) |
| Technical complexity | Low (static content app) | Medium (data normalization + dashboard) |
| User clarity | Very clear (specific teen, specific journey) | Clear (researcher, grant application workflow) |
| Demo risk | Low if content is curated carefully | Medium if data access fails |
| Harm potential | Low if no PII stored; work permit accuracy matters | Low if no clinical claims; citation accuracy matters |
| Continuation path | Named champions possible (Girls For A Change, OCWB) | Named partners possible (Richmond health nonprofits) |

---

## Output your decision here

After discussion, record your decision in `99_templates/decision_memo.md`.

Chosen problem: ________________
Reason: ________________
What we are explicitly NOT building: ________________
