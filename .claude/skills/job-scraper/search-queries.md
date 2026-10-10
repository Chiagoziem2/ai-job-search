# Search Queries for Job Scraper

<!-- SETUP: Customize these queries based on your skills, target roles, and location -->

## Installed portal CLIs (primary for `/scrape`)

`/scrape` discovers every portal skill under `.agents/skills/*/SKILL.md` and runs its CLI first. Shipped country-agnostic CLIs include `linkedin-search` and `freehire-search`; Danish demos and any skill you add with `/add-portal` are included the same way. You do **not** need a matching `site:` line below for those CLIs to run.

The `site:` query templates in this file are the **WebSearch fallback** — for portals without a CLI, company career pages, or when a CLI fails.

**Language scope:** write every query category in every language listed in your CLAUDE.md Languages table (typically 1-2, sometimes more). A posting requiring a language you have *not* declared, as a job condition, is excluded before scoring; a posting requiring a *higher level* than you declared in a language you *do* work in is flagged for your own judgment, not excluded — see `04-job-evaluation.md`'s Language Gate, the single source of truth for this rule. Translate each category's keywords rather than machine-translating word-for-word (e.g. "Frontend Developer" -> "Desarrollador Frontend", not a literal word-for-word translation) if you work in more than one language.

## Search Sites

Primary (your market's job boards - scaffold one with `/add-portal`):
- **linkedin.com/jobs** - LinkedIn job listings (filter: United Kingdom / Birmingham / London / Remote); also covered by the `linkedin-search` CLI
- **jobs.nhs.uk** - NHS Jobs, the only board carrying most NHS trust and NHS England data roles
- **jobs.ac.uk** - UK academic jobs; university health-informatics and HDR UK hub roles
- **uk.prosple.com / brightnetwork.co.uk / gradcracker.com** - UK student internship and placement aggregators

Secondary (company career pages via Google):
- Direct Google searches with `site:` filters for known target companies
## Search Sites

Primary (UK market):
- **linkedin.com/jobs** — filter: United Kingdom / Birmingham / London / Remote; also covered by the `linkedin-search` CLI
- **jobs.nhs.uk** — NHS Jobs. The only place most NHS trust and NHS England data roles are advertised. No CLI; WebSearch/WebFetch only.
- **jobs.ac.uk** — UK academic jobs. Where university health-informatics and HDR UK hub roles appear. No CLI; WebSearch/WebFetch only.
- **uk.prosple.com**, **brightnetwork.co.uk**, **ratemyplacement.co.uk**, **gradcracker.com** — UK student internship/placement aggregators. These, not general job boards, are where structured summer internships surface.
- **freehire.me** — tech-first aggregator (`freehire-search` CLI). Low yield for health data science; it indexes software/ML engineering roles, not academic schemes.

Secondary (employer career pages via WebSearch `site:` filters) — see the watchlist below.

---

## ⚠️ Read this before running `/scrape` for health data science

**Keyword scraping of job boards is the wrong primary instrument for this candidate's target category, and `/scrape` alone will under-deliver.** Three structural reasons:

1. **The targets are annual schemes, not rolling vacancies.** HDR UK internships, Wellcome Biomedical Vacation Scholarships, NIHR INSIGHT/INSPIRE, Amgen Scholars, and university summer research programmes recruit once a year against a fixed deadline and are advertised on the funder's or university's own page — frequently never on a job board at all. A 14-day recency window is actively harmful here: it hides a scheme whose page went up three months before its deadline.
2. **The availability window is one block per year.** The candidate can only take a summer-vacation placement, so the live question is almost never "what is posted today" but "which cycle closes next". That is a **deadline watchlist** problem, not a search problem.
3. **"Intern" is often not in the title.** The relevant words are *vacation scholarship*, *summer studentship*, *bursary*, *placement*, *INSIGHT*, *undergraduate research opportunity*.

**So: run the watchlist below as the primary mechanism, and `/scrape` as the supplement** that catches commercial internships (pharma, health-tech, NHS) which genuinely do appear as postings.

---

## Scheme Watchlist (primary mechanism)

Check each source page directly — do not rely on a board index. Verify every date on the source's own page before acting; cached search results for annual schemes are frequently a cycle out of date.

| Scheme / host | Source to check | Typical cycle | Notes |
|---|---|---|---|
| HDR UK — Health Data Science Black Internship Programme | hdruk.ac.uk → Study and train | Opens autumn, closes early Jan, runs ~8 weeks late Jun–Aug | Eligibility restricted to Black applicants; UK-based; no visa sponsorship. Hosts have included Genomics England, Our Future Health, the Alan Turing Institute. |
| HDR UK — Undergraduate Summer Internship / HDR UK–Wellcome Biomedical Vacation Scholarship | hdruk.ac.uk; hdrmidlands.org.uk | Opens spring for that summer | **Already held in 2026.** Many hosts bar previous vacation-scholarship holders — check each host's rules before re-applying. |
| HDR UK Midlands / PIONEER (Birmingham) | hdrmidlands.org.uk | Varies | Local to Birmingham — worth a direct email even with no advertised call. |
| NIHR INSIGHT (absorbing INSPIRE from 2027) | nihr.ac.uk → INSIGHT programme; **Aston Medical School directly** | Regional programmes, 3-year funding rounds | Aston holds NIHR funding for internships. Ask Aston Medical School's research/UG office — this is an internal route, not a public posting. |
| Health Data Insight (HDI) | healthdatainsight.org.uk | 2–3 months from July | Open to undergraduates; ~£2,066/month in the last cycle. |
| NHS England Data Science | nhsengland.github.io/datascience | Annual | **PhD students only** — not eligible. Monitor only in case an undergraduate route opens. |
| Genomics England / Our Future Health / UK Biobank | their own careers pages | Ad hoc | Run occasional bioinformatics and data internships outside the HDR UK scheme. |
| Alan Turing Institute | turing.ac.uk → internships | Annual, PhD-only at present | Ran an undergraduate pilot in 2024; watch for its return. |
| Pharma R&D data science placements — AstraZeneca, GSK, Roche | each firm's UK early-careers page | Opens Sept–Mar for that summer; rolling review | Genuine postings — these the scraper *can* find. Fastest-closing of everything here. |
| University summer research bursaries (Birmingham, Nottingham, Warwick, Leicester) | each university's UG research opportunity page | Spring | Nottingham is warm ground — existing TRExt supervisor relationship. |

**Also non-obvious and high-yield:** email the TRExt / Lettuce supervisor at Nottingham and the Aston Medical School research lead directly. A returning intern with a shipped tool and a conference record is the cheapest hire a group can make, and these placements are routinely arranged without ever being advertised. Treat this as a first-class channel, not a fallback.

---

## Query Categories (supplement, for `/scrape`)

Written in English only — the Languages table declares English alone.

### Priority 1: Health data science / clinical informatics internships

```
site:linkedin.com/jobs "health data science" intern United Kingdom
site:linkedin.com/jobs "clinical informatics" intern OR placement United Kingdom
site:jobs.ac.uk "health data" internship OR studentship OR bursary undergraduate
site:jobs.nhs.uk data science intern OR placement OR "work experience"
"health data science" ("summer internship" OR "vacation scholarship" OR "summer studentship") UK 2027
```

### Priority 2: Applied ML / data science on clinical data

```
site:linkedin.com/jobs "data science" intern Birmingham OR London OR Manchester
site:uk.prosple.com data science internship 2027
site:gradcracker.com data science OR "machine learning" placement
("clinical AI" OR "medical imaging" OR "digital health") intern UK 2027
```

### Priority 3: Pharma / biotech R&D data science placements

```
site:careers.astrazeneca.com data science internship UK 2027
site:jobs.gsk.com internship data OR analytics UK 2027
site:careers.roche.com internship data science UK
("AstraZeneca" OR "GSK" OR "Roche" OR "Novartis") "summer internship" 2027 data UK
```

### Priority 4: Evidence synthesis / research assistant (uses the strongest part of the record)

```
site:jobs.ac.uk "systematic review" research assistant OR intern undergraduate
site:jobs.ac.uk "evidence synthesis" summer OR vacation OR studentship
```

## Location Filter

When evaluating results, verify the job location is within reasonable commute distance from your home. Define acceptable areas:
- **Birmingham and the West Midlands** - term-time base; no relocation needed
- **Anywhere in the UK for a summer-vacation placement** - the 2026 Nottingham internship is precedent; most schemes include a travel and accommodation bursary
- **Fully remote** - acceptable
- CONFIRM any location the candidate would actually rule out. The repo treats this list as a hard filter, so a permissive list means nothing is filtered.

## Language Filter

Your working languages and levels are in CLAUDE.md's Languages table. When filtering scraped results, apply `04-job-evaluation.md`'s Language Gate: a posting requiring a language you haven't declared at all is excluded; a posting requiring a higher level than you declared in a language you do work in is not excluded, flag it clearly instead (see `job-scraper/SKILL.md`'s Step 3 "Quick Fit Assessment" for how the flag surfaces in `/scrape` output). Postings simply *written* in a language you don't work in, that don't require it on the job, are fine.

## Date Filter

Only include jobs posted within the last 14 days, or with an application deadline that has not yet passed. If a posting date cannot be determined, include it but flag as "date unknown".

## Adapting Queries

If the user specifies a focus area, select queries from the matching category and also generate 2-3 custom queries for that focus. For example:
- "/scrape [focus_area]" -> relevant category queries + custom focus-specific queries
