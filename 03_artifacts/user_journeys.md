# User Journey Maps (Draft — needs verification)

Note: Journeys include observations from the working session and rubric context, pending field verification. Each friction point should reference an `evidence_log.md` id when verified.

---

## Journey 1 — 16-year-old Richmond teen trying to find and apply for a first summer job

**User goal:** Find a summer job, understand what I need to do, and successfully apply.

**Background:** Jaylen is 16, lives in the East End, attends Richmond public school, does not have a car, and has no prior work experience. No family member has navigated formal youth employment before.

**Steps taken:**

1. Hears from a friend that "the City has summer jobs" — searches online
2. Lands on City of Richmond website; finds OCWB page but cannot tell if the program is still open or how to apply
3. Searches "summer jobs for teens Richmond VA" — gets mixed results including national job boards, expired listings, and one local org
4. Finds Girls For A Change and Boys & Girls Club pages but cannot tell age eligibility or whether applications are still open
5. Asks a school counselor — counselor knows of one program but doesn't have current information
6. Realizes she needs a work permit — searches "Virginia work permit for minors" — finds a PDF from DOLI but doesn't understand the parental consent section
7. Tries to figure out how to get to a job site — checks GRTC app but isn't sure which bus goes near the employer

**Friction points:**

- No single place lists all available youth employment programs with current status
- Age eligibility and application windows are buried or missing from most program pages
- Virginia work permit process is described in legal language, not plain language
- Parental consent requirements are unclear — what form? Who signs? Where does it go?
- Transportation to employer is a real barrier; teen cannot self-drive and transit takes planning
- School counselor lacks current, verified program information

**User questions at each step:**

- What programs are actually open right now, and am I old enough to apply?
- What documents do I need before I can start a job at 16?
- What is a work permit and how do I get one?
- Do my parents need to sign something? What?
- How do I get to this job on the bus?
- What should I put on a resume if I've never worked before?

**Prototype opportunities:**

- Youth employment pathway guide: step-by-step from "I want a job" to "I am ready to apply"
- Work permit and document checklist in plain language (link to official DOLI form, not a reproduction)
- Program directory with age eligibility, application status, and location
- Transit context: "This program is near the X bus line"

---

## Journey 2 — Maternal health researcher at a Richmond nonprofit recreating VDH data pulls for the fifth time

**User goal:** Compile current maternal health indicators for Richmond for a grant application due in three weeks.

**Background:** Keisha is a program analyst at a Richmond health advocacy nonprofit. She has done this analysis before — last year, and the year before. Each time she starts from scratch because there is no shared workspace, no agreed-upon indicator set, and no standardized methodology across organizations.

**Steps taken:**

1. Opens a new spreadsheet — the same one she built last year, now outdated
2. Navigates to VDH vital records site — finds maternal mortality data but in a different format than last year; must re-map columns
3. Downloads ACS tables from Census Bureau — has to remember which table codes correspond to which indicators; takes 45 minutes
4. Looks for Kids Count data — finds the portal; downloads but finds the 2024 indicators are in a different structure than 2022
5. Emails a colleague at a City agency asking what numbers they used for their last report — waits two days for a response
6. Colleague sends different numbers — small discrepancy in the infant mortality rate; neither can tell which is authoritative
7. Writes a note in the spreadsheet: "CHECK THIS NUMBER"
8. Submits grant with a footnote disclaimer about data sources

**Friction points:**

- No shared indicator definitions across organizations
- VDH data format changes year to year — no stable schema
- ACS table codes are not intuitive; require prior knowledge or hours of lookup
- No shared data workspace or version-controlled indicator set
- Manual reconciliation of discrepancies is time-consuming and unresolved
- Grant funders receive inconsistent numbers across multiple Richmond applications

**User questions at each step:**

- What is the current maternal mortality rate for Richmond, and which source do I use?
- Are we all using the same definition of "maternal mortality"?
- Why does my number for infant mortality not match the City's number?
- Is there a place where someone has already done this data pull that I can build on?
- Can I trust this number enough to put it in a grant application?

**Prototype opportunities:**

- Shared indicator dashboard: standard set of 6–10 maternal health indicators, each linked to a named public source with access date
- Data aggregator: pull from VDH, ACS, Kids Count on demand and display in a consistent format
- Indicator dictionary: plain-language definition for each metric with source, methodology note, and caveats
- Version log: "last updated" and "data source vintage" for each indicator
