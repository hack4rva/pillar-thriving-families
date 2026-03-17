# Recommended Architectures - Thriving Families

---

## Architecture 1 — Static Content App (Shapes A, B)
**Best for:** Youth pathway guide, job readiness checklist
**Complexity:** Low
**Stack:** HTML/CSS/JS, React, or Vue; optionally Next.js for static generation

### Components
- Static JSON data file: program list, document checklist, labor law summary
- Frontend framework with filter/wizard UI
- No backend required; no database
- Deploy to GitHub Pages, Netlify, or Vercel (free tier)

### Data flow
```
curated JSON (programs, checklist items, law summary)
  → frontend wizard/filter
  → user-facing display with links to official sources
```

### Notes
All content is curated and version-controlled in the repo. No API calls at runtime. No user data stored. Simple to deploy and demo. Update content by editing the JSON file.

---

## Architecture 2 — Guided Wizard / Decision Tree (Shapes A, B, C)
**Best for:** Pathway guide with branching logic (age, interest, location)
**Complexity:** Low-Medium
**Stack:** React or plain JS; state machine or simple if/then logic

### Components
- Multi-step form with branching logic
- Curated content object (programs, requirements, tips)
- Result display with links to official sources
- Optional: URL-based state so teens can share their results

### Data flow
```
user inputs (age, interest, location)
  → filter/match against curated content
  → personalized result with links
```

### Notes
Keep branching logic simple: age group (14–15 vs 16–17 vs 18), interest category (3–5 options), location (broad areas: East End, Northside, etc.). Do not build an eligibility engine — show options and tell users to verify with each program.

---

## Architecture 3 — Data Dashboard (Shape D)
**Best for:** Maternal health data aggregator
**Complexity:** Medium
**Stack:** Python (Pandas + Streamlit or Plotly Dash) or JavaScript (Observable, Vega-Lite)

### Components
- Data ingestion scripts: ACS API pull, VDH CSV parser, Kids Count CSV parser
- Normalization layer: standard schema across sources
- Dashboard UI: indicator cards with source, date, definition
- Optional: simple bar charts for trend view

### Data flow
```
ACS API / VDH download / Kids Count CSV
  → normalization script
  → standard indicator schema
  → dashboard display
```

### Notes
Verify all data access on Friday evening before committing to this architecture. ACS API is stable (free key from data.census.gov). VDH format may require manual inspection. Kids Count CSV is straightforward. Budget 4–6 hours for data work before UI development.

---

## Architecture 4 — Static Reference Site (Shape E)
**Best for:** Shared indicator dictionary
**Complexity:** Low
**Stack:** Static site generator (11ty, Hugo, Jekyll) or plain HTML; or a searchable JSON rendered with Lunr.js

### Components
- Curated indicator JSON/YAML: name, definition, source, table code, vintage, caveats, URL
- Search interface (client-side with Lunr.js or simple filter)
- Individual indicator pages or cards

### Data flow
```
curated indicators JSON
  → search/filter interface
  → indicator detail view with source citation
```

### Notes
This is the lowest-risk architecture for maternal health. No live data access needed. The curation work is the valuable output. Can be extended with live data later.

---

## Shared Notes for All Architectures

### What to avoid
- Backend databases: not needed for any shape; adds complexity with no demo benefit
- User authentication: no user accounts; no stored user data
- Real-time data for youth employment: the data does not exist in structured form
- Third-party job boards (Indeed, LinkedIn): not Richmond-specific and not the problem

### Demo reliability tips
- Use hardcoded/curated data rather than live API calls during the demo — APIs can fail
- Have a screenshot fallback for any API-dependent feature
- Test on the venue's network before the demo (VCU Snead Hall wifi)
- Keep the demo path to 3–5 clicks maximum

### Privacy reminder (youth employment)
- No form inputs stored, logged, or transmitted
- No cookies or tracking
- No user accounts or registration
- If a teen checks off items on a checklist, that state lives only in their browser session
