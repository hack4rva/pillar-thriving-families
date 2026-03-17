# 48-hour Richmond Maternal Health MVP — Fast, Resilient Data + Dashboard Plan

## Executive Summary

To deliver a functional, high-impact Richmond maternal health data aggregator MVP within a strict 48-hour window, the strategy must prioritize resilience, speed, and pre-curated data over complex live engineering. The optimal approach anchors the MVP on the Virginia Department of Health (VDH) Maternal and Child Health (MCH) Indicators for core outcomes [1], supplemented by the Census Bureau's American Community Survey (ACS) for Social Determinants of Health (SDOH) context. 

Because public data portals can be brittle or slow to access, the build path must include immediate parallel contingencies: utilizing the Kids Count Data Center as a proxy data source [2] and implementing a Streamlit-based UI that defaults to local CSV snapshots if live API calls fail [3] [4]. By restricting the scope to 6–8 highly relevant indicator cards and standardizing the ingestion pipeline early, you can guarantee a working, interactive demo that tells a complete "what and why" story of maternal health in Richmond, regardless of external network conditions at demo time.

## MVP Goal and Scope

The primary objective is to ship a Richmond-specific maternal health dashboard in 48 hours that demonstrates both the "what" (health outcomes) and the "why" (social determinants). The scope is strictly limited to 6–8 indicator cards sourced from VDH and ACS, utilizing Kids Count as a contingency source. The MVP will feature offline data snapshots to ensure a 100% reliable demo, avoiding the common pitfall of live API failures during presentations.

## Data Access Plan with Hour-by-Hour Estimates

To hit the 48-hour target, data acquisition must be parallelized. API keys should be requested immediately, and local snapshots must be saved as soon as data is successfully extracted to stabilize the demo environment.

| Workstream Phase | Cumulative Time | Tasks & Objectives | Risk Mitigation |
| :--- | :--- | :--- | :--- |
| **Phase 1: Setup & Keys** | T+0–1h | Apply for Census API key; set up project repo/venv; scaffold Streamlit app [5]. | **Risk:** API key email delay. **Mitigation:** Develop with limited unauthenticated calls initially. |
| **Phase 2: ACS SDOH Pulls** | T+1–3h | Script ACS pulls for tables S1701, S2701, S1501, S1301, S1901, B03002. Test for Richmond (state=51, county=760). | Use 5-year estimates if 1-year data is too sparse for specific cross-sections. |
| **Phase 3: VDH Outcomes** | T+2–6h | Locate CSV/API behind VDH MCH dashboard [1]. If no API, export tables or scrape HTML. Snapshot to CSV. | **Risk:** Brittle formats. **Mitigation:** Use robust pandas parsing. |
| **Phase 4: Kids Count Proxy** | T+2–4h | Filter and export overlapping indicators for Richmond city from Kids Count [2] [6]. Snapshot to CSV. | Run in parallel with VDH extraction to ensure a backup exists. |
| **Phase 5: Normalization** | T+4–8h | Build a normalization pipeline to produce unified CSVs per `indicator_id`. | Map all geographies to FIPS 760 to prevent join failures. |
| **Phase 6: UI & Dashboard** | T+8–18h | Build UI cards, charts, source footers, and error handling in Streamlit [7]. | Rely on `st.cache_data` to speed up reload times [8]. |
| **Phase 7: QA & Polish** | T+18–24h | QA data definitions, implement small-count flags (N<20) [1], polish styles, write runbook. | Ensure all caveats are visible in tooltips. |
| **Phase 8: Buffer & Dry Run** | T+24–48h | Buffer for VDH delays; swap in Kids Count proxies if needed; dry-run the offline demo. | Test the app with the internet disconnected to verify fallbacks. |

*Takeaway: Front-loading the data extraction and immediately saving local snapshots ensures that the remaining 24+ hours can be dedicated entirely to UI refinement and narrative building.*

## Data Sources and Access Methods

A three-source blend maximizes both speed and resilience. By keeping the geographic identifier (FIPS) consistent across all sources, the data can be seamlessly joined in the UI.

| Data Source | Content Type | Access Method & Strategy | Key Notes & Caveats |
| :--- | :--- | :--- | :--- |
| **VDH MCH Indicators** | Core Outcomes | Find downloadable datasets via linked dashboards. If absent, export CSV manually or scrape tables [1]. | Uses maternal county of residence. 2023 is the most recent year. Counts <20 must be interpreted with caution [1]. |
| **Kids Count Data Center** | Backup / Validation | Filter Geography to Virginia, then Locality to Richmond city. Select indicators and download raw CSV [2] [6]. | Excellent proxy for low birthweight, preterm, and teen births. Definitions may vary slightly from VDH [9]. |
| **Census ACS** | SDOH Context | REST API query using `get=vars&for=county:760&in=state:51&key=KEY`. Snapshot JSON to CSV. | Richmond city is county-equivalent FIPS 760. |

*Takeaway: Rely on VDH for the primary narrative, but keep Kids Count data normalized and ready to swap in if VDH extraction hits a roadblock.*

## ACS Indicators to Pull

The American Community Survey (ACS) provides immediate Social Determinants of Health (SDOH) context at the same geographic level as VDH. Using ACS "Subject" tables provides ready-made percentages, saving calculation time.

| Indicator Category | ACS Table ID | Example API Query Pattern (Richmond City) | Rationale |
| :--- | :--- | :--- | :--- |
| **Poverty** | S1701 | `/acs/5year/subject?get=NAME,S1701_C02_001E&for=county:760&in=state:51` | Captures poverty rates for families with children. 5-year offers stability. |
| **Health Insurance** | S2701 | `/acs/1year/subject?get=NAME,S2701_C05_XXXE&for=county:760&in=state:51` | Identifies uninsured populations. Will require approximating women 18–44 using available age/sex bins. |
| **Education** | S1501 | `/acs/5year/subject?get=NAME,S1501_C02_0XXE&for=county:760&in=state:51` | Tracks educational attainment (e.g., <HS for women 25–34). |
| **Fertility** | S1301 | `/acs/1year/subject?get=NAME,S1301_C01_0XXE&for=county:760&in=state:51` | Contextualizes birth rates for women 15–50 in the past 12 months. |
| **Income** | S1901 | `/acs/1year/subject?get=NAME,S1901_C01_012E&for=county:760&in=state:51` | Provides median household income for baseline economic context. |
| **Race/Ethnicity** | B03002 | `/acs/1year/detail?get=B03002_001E,...&for=county:760&in=state:51` | Provides demographic denominators to align with VDH's Hispanic/Non-Hispanic and single-race categories [1]. |

*Takeaway: Use 1-year estimates for recency where Richmond's population supports it, but default to 5-year estimates for stable percentages on granular cross-sections.*

## VDH Outcomes and Handling Inconsistent Formats

The VDH MCH dashboard provides critical indicators including infant mortality, late/no prenatal care, low birthweight, maternal smoking, Medicaid births, preterm birth, teen pregnancy, and WIC use [1]. However, public portal CSV exports are notoriously inconsistent, often containing malformed rows, changing headers, or trailing metadata.

To build a resilient loader in pandas, you must anticipate bad lines. 

**Robust CSV Parsing Strategy:**
1. **First Pass:** Attempt standard ingestion using `pd.read_csv(filepath, dtype=str)` to prevent aggressive type inference from failing on mixed columns [10].
2. **Fallback for Bad Lines:** If the file contains malformed lines (e.g., too many fields), utilize the `on_bad_lines` parameter. Setting `on_bad_lines='skip'` will bypass errors, or you can pass a callable function to programmatically fix the row (e.g., `lambda x: x[:-1]`) [10] [11]. Note that using a callable requires `engine='python'` [11].
3. **Encoding Issues:** If standard UTF-8 fails, implement a fallback to `encoding='latin1'` or `encoding='iso-8859-1'` [10] [11].
4. **Data Quality Flags:** VDH explicitly notes that counts lower than 20 and their associated rates should be interpreted with caution [1]. The ingestion script must flag any row where `count < 20` with a `data_quality='caution_small_n'` tag.

## Kids Count Virginia Contingency

If VDH data access lags or requires complex scraping that threatens the 48-hour timeline, the Annie E. Casey Foundation's Kids Count Data Center serves as a rapid proxy [2]. 

**Extraction Steps:**
1. Navigate to the Virginia Data Center [2].
2. Filter by Location: Select "Virginia" and refine to "By city" -> "Richmond" [2].
3. Select overlapping indicators: Low birth-weight babies, Preterm births, and Teen births [2] [6].
4. Use the "Download Raw Data" feature to export the CSV [6].
5. Map this data to the exact same normalized schema intended for VDH. Label the source clearly to manage expectations regarding differing rate denominators [9].

## Normalized Data Schema

Cross-source harmonization is the most common failure point in rapid data aggregation. Adopting a strict, tidy wide-to-long schema ensures that swapping sources (e.g., from VDH to Kids Count) requires zero code changes in the UI.

**Proposed Schema Fields:**
* **Identifiers:** `indicator_id`, `geo_id` (FIPS 760), `year`
* **Descriptors:** `indicator_name`, `geo_name` (Richmond city), `unit` ('rate_per_1k', 'percent'), `measure_type`
* **Values:** `value` (float), `numerator`, `denominator`
* **Disaggregations:** `sex`, `age_group`, `race_ethnicity` (Mapped to VDH's Hispanic/Non-Hispanic and single-race categories [1])
* **Provenance & Meta:** `source`, `source_url`, `last_updated`, `definition`, `data_quality` (e.g., 'caution_small_n')

## UI Stack Decision

Choosing the right technology stack is critical for a 48-hour turnaround. The stack must require minimal boilerplate, handle data natively, and degrade gracefully.

| Technology Stack | Setup Time | Data Handling | Error/Fallback UX | Verdict |
| :--- | :--- | :--- | :--- | :--- |
| **Streamlit** | ~15 mins (`pip install streamlit`) [3] [5] | Native pandas integration; built-in caching (`st.cache_data`) [8] [4]. | Excellent. Built-in `st.error` and `st.warning` components [7]. | **Recommended.** Fastest zero-to-demo path for Python developers. |
| **Observable** | Minutes (Browser-based) [12] | Requires JS/D3; loads via file attachments or APIs [13] [14]. | Requires custom JS UI for error states. | Good for secondary showcases, but slower for rapid data wrangling. |
| **Static HTML + Chart.js** | ~20 mins (CDN include) [15] | Manual data prep required in JS; no native dataframe support. | Minimal out-of-the-box error UI. | Too much manual plumbing for a 48-hour MVP. |

*Takeaway: Streamlit is the definitive choice. It allows the developer to stay entirely in Python, utilizes pandas for on-the-fly data adjustments, and provides first-class caching and error-handling components.*

## Minimum Dashboard Specification

To prevent scope creep, the MVP dashboard will be restricted to a compact grid of 6–8 cards that mix outcomes and SDOH context.

**Required Cards:**
1. **Infant Mortality Rate:** (per 1,000 live births) — Source: VDH 2023. *Note: Display small-n caution if applicable* [1].
2. **Low Birthweight:** (%) — Source: VDH 2023 [1].
3. **Late or No Prenatal Care:** (%) — Source: VDH 2023 [1].
4. **Teen Pregnancy Rate:** (per 1,000 females 15-19) — Source: VDH 2023 or Kids Count proxy [1] [2].
5. **Poverty Rate (Families with Children):** (%) — Source: ACS S1701.
6. **Uninsured Women (18–44):** (%) — Source: ACS S2701.
7. **Educational Attainment (<HS, Women 25–34):** (%) — Source: ACS S1501.
8. **Median Household Income:** ($) — Source: ACS S1901.

**UI Elements per Card:**
* Primary metric value with a trend sparkline (if >3 years of data is available).
* Hyperlinked source citation footer.
* Tooltip containing the exact definition and denominator.
* Data-quality warning tags (e.g., "Caution: Count < 20").

## Build Patterns and Code Sketches

To ensure the demo survives network failures, wrap every data loader in a fetch-then-fallback pattern using Streamlit's caching and error components.

```python
import streamlit as st
import pandas as pd

# Cache the data to prevent redundant API calls and speed up the UI
@st.cache_data(ttl=86400) # Cache for 24 hours
def fetch_vdh_data(indicator_id):
 try:
 # Attempt live API or primary CSV fetch here
 #...
 pass
 except Exception as e:
 # Graceful degradation: surface a warning and load the local snapshot
 st.warning(f"Live VDH data unavailable for {indicator_id}. Loading local snapshot.")
 return pd.read_csv(f"data/snapshots/vdh_{indicator_id}.csv")
```
*Note: Use `st.cache_data` for dataframes that return copies, rather than `st.cache_resource` which is meant for singletons like database connections [8] [16].*

## Fallback Plan if Data Access Fails

If VDH data access takes longer than 6 hours to resolve (e.g., due to complex scraping protections or missing endpoints), pivot the content strategy rather than stalling the code build.

1. **The Proxy Pivot:** Substitute the missing VDH outcomes with Kids Count equivalents [2]. Mark the cards clearly with "Source: Kids Count (Proxy)" to maintain transparency.
2. **The Content-Only Dictionary:** For VDH indicators that have no Kids Count equivalent (e.g., WIC use during pregnancy [1]), render the card in a "Pending" state. 
 * Display the indicator label.
 * Set the value to `Null` or `N/A`.
 * Display the official VDH definition: *"Live births where the mother reported buying food supported by WIC during the pregnancy"* [1].
 * Add a note: *"Awaiting live VDH data integration; definition shown for context."*
3. **Offline Mode:** Build a toggle in the Streamlit sidebar for "Offline Demo Mode" that intentionally bypasses all API calls and forces the app to read from `/data/snapshots/`. This guarantees a flawless presentation.

## Inferences

* **Inference:** Census API key emails typically arrive within minutes to an hour. Development can begin immediately using limited unauthenticated calls, dropping the key into Streamlit's `secrets.toml` once it arrives.
* **Inference:** Because VDH reports data based on the maternal county/city of residence [1], ACS queries must use the county-equivalent FIPS code for Richmond city (`for=county:760&in=state:51`) to ensure an apples-to-apples geographic comparison.
* **Inference:** ACS S2701 age/sex bins may not map perfectly to the standard 18–44 maternal age bracket. The build will require approximating using the nearest available Census bins, which must be explicitly documented in the UI tooltips.

## Unknowns

* **VDH Backend Stability:** It is unknown whether the VDH MCH dashboard sits atop a stable, documented API endpoint or if it will require brittle HTML table scraping.
* **ACS Variable IDs:** The exact, granular variable IDs for specific sub-bins (e.g., uninsured women specifically aged 18–44 in S2701) remain unknown until the ACS metadata is queried.
* **Disaggregation Scope:** While VDH offers race/ethnicity breakdowns (Hispanic/Non-Hispanic and single-race categories) [1], it is unknown if there is sufficient time within the 48-hour window to implement interactive demographic toggles in the UI, or if the MVP should stick to top-line locality averages.

## References

1. *Maternal & Child Health Indicators - Data*. https://www.vdh.virginia.gov/data/maternal-child-health/mch-indicators/
2. *Virginia Child and Family Well-Being - Kids Count*. https://datacenter.aecf.org/data?location=VA
3. *Streamlit • A faster way to build and share data apps*. https://streamlit.io/
4. *Caching overview - Streamlit Docs*. https://docs.streamlit.io/develop/concepts/architecture/caching
5. *Install Streamlit - Streamlit Docs*. https://docs.streamlit.io/get-started/installation
6. *Total teen births | KIDS COUNT Data Center*. https://datacenter.aecf.org/data/tables/6053-total-teen-births
7. *st.error - Streamlit Docs*. https://docs.streamlit.io/develop/api-reference/status/st.error
8. *st.cache_data - Streamlit Docs*. https://docs.streamlit.io/develop/api-reference/caching-and-state/st.cache_data
9. *Virginia Data | Voices for Virginia's Children*. https://vakids.org/kids-count/virginia-data
10. *pandas.read_csv — pandas documentation - PyData |*. https://pandas.pydata.org/docs/reference/api/pandas.read_csv.html
11. *python - Pandas dataframe read_csv on bad data - Stack Overflow*. https://stackoverflow.com/questions/33440805/pandas-dataframe-read-csv-on-bad-data
12. *Notebooks | Observable documentation*. https://observablehq.com/documentation/notebooks/
13. *Three ways to ingest json / CSV data via Observable file attachments / Joe Murphy | Observable*. https://observablehq.com/@freejoe76/three-ways-to-ingest-json-csv-data-via-observable-file-attac
14. *Project structure | Observable Framework*. https://observablehq.observablehq.cloud/framework/project-structure
15. *Getting Started | Chart.js*. https://www.chartjs.org/docs/latest/getting-started/
16. *st.cache_resource - Streamlit Docs*. https://docs.streamlit.io/develop/api-reference/caching-and-state/st.cache_resource