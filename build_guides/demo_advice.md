> **Note:** This research was generated using AI assistance (Claude + Parallel.ai) with human expert review. See [methodology](../docs/methodology.md) for details.

# Demo Advice - Thriving Families

---

## Core principle
Judges evaluate your understanding of the problem as much as your code. A well-framed demo of a simple, honest tool beats an ambitious demo of a half-built platform.

---

## Demo structure (3–5 minutes)

### 1. Problem hook (30–45 seconds)
Open with a real, concrete scenario — not a statistic.

**Youth Employment example:**
"Jaylen is 16, lives in the East End, wants her first summer job. She spends two hours searching and still doesn't know what programs she qualifies for, what documents she needs, or how to get there on the bus. That's what we're solving."

**Maternal Health example:**
"Keisha is a researcher at a Richmond nonprofit. She's done the same data pull from VDH and Census four times. Each time it takes a full day, and she still ends up with numbers that don't match her colleague's. That's the problem."

### 2. Who and why (30 seconds)
State the user clearly. State what they cannot do today that they will be able to do with your tool.

### 3. Live demo (2–3 minutes)
Walk through your tool's core path in 4–5 steps maximum. Use a real scenario — do not demo "test data."

**Youth Employment demo path:**
- User selects age: 16
- User selects interest: customer service / retail
- Tool shows: 3 matching programs with eligibility confirmed
- Tool shows: document checklist with 5 items
- Tool shows: "what is a work permit and how do I get one" — links to DOLI

**Maternal Health demo path:**
- Researcher opens dashboard
- Sees: Richmond maternal mortality rate with source (VDH) and date
- Sees: Infant mortality rate with source (VDH) and definition
- Sees: Poverty rate context with source (ACS)
- Clicks: "What does this number mean?" → plain-language definition appears

### 4. Credibility and limits (30 seconds)
Tell judges what your tool does NOT do and why.

"This tool does not store any personal information about teens. It does not make eligibility determinations. Every item links to an official source so users can verify before acting. We are not replacing counselors — we are giving teens a starting point."

"This dashboard does not provide medical guidance. It aggregates public data so researchers can spend less time on compilation and more time on action. The numbers are only as current as the underlying sources."

### 5. What's next (30 seconds)
Name one real person or organization you would want to partner with to continue.

"We'd want to share this with Girls For A Change and OCWB to see if they'd list their programs here and keep them updated."

---

## Common judge questions and how to answer them

**"How do you keep the data current?"**
Youth: "The program directory is curated content — it needs a community partner to maintain it, which is why we'd partner with Girls For A Change or OCWB."
Maternal: "ACS is updated annually via API. VDH data is updated on a publication schedule — the dashboard shows the vintage date so users always know how current the data is."

**"What happens when a teen tries to apply and a program is full?"**
"The tool always directs teens to the program's official website to verify current availability. We never claim a program is definitely open — we show what exists and link to the source."

**"Is this approved by the City?"**
"This is a prototype. It uses public information. We would need to work with OCWB and program partners to validate content and explore an official hosting arrangement."

**"What about teens without smartphones?"**
"That's a real gap. The tool is designed to be mobile-friendly, but it doesn't solve the access problem for teens without devices. A printed version or a school kiosk version would be meaningful extensions."

---

## What to avoid in the demo

- Do not demo an empty state or error state
- Do not show raw API responses or JSON
- Do not narrate technical implementation details ("we used React because...")
- Do not claim the tool will be deployed immediately or is City-approved
- Do not make your demo dependent on live internet access — have a local fallback

---

## Rubric alignment notes

**D1 Clarity:** State the user and problem in your first sentence.
**D2 Scope:** Name what you explicitly did not build and why.
**D3 Data readiness:** Acknowledge the data gap and explain how you addressed it (curation strategy).
**D4 Champion:** Name a real potential partner by name.
**D5 Population and impact:** Connect to a real Richmond population with specificity.
**D6 Operating environment:** Show you understand what already exists (OCWB, Girls For A Change, VDH).
**D7 Success criteria:** State what success looks like: "a teen goes from not knowing to knowing what to do next."
**D8 Accessibility:** If you addressed mobile, language accessibility, or low-bandwidth — say so.
