---
framework_version: 1.1.1
---

# Candidate Profile

<!-- Populated 2026-10-10 from Chiagoziem_Nneke_CV.pdf (user-supplied). -->
<!-- Fields marked CONFIRM were not stated on the CV and must not be used in an -->
<!-- application until the candidate confirms them. Do not invent values for them. -->

## Identity
- **Name:** Chiagoziem Nneke
- **Location:** Birmingham, United Kingdom (studying at Aston University)
- **Phone:** CONFIRM — not on the supplied CV. Needed: most UK application forms require it, and the ATS check in CLAUDE.md requires a phone number in the PDF text layer.
- **Email:** cnneke@yahoo.com (the address on the CV). Account email on file: cnneke13@gmail.com — CONFIRM which should appear on applications.
- **LinkedIn:** https://linkedin.com/in/chiagoziem-nneke-88933224b
- **GitHub:** https://github.com/Chiagoziem2
- **Status:** Medical student, Year 3 of 5 (MBChB 2024–2029). Available for summer vacation placements only; term-time work is constrained by a clinical timetable.
- **Constraints:**
  - **Availability window:** summer vacation. The next realistic full placement is **summer 2027** (summer 2026 is already spent on the Nottingham internship). CONFIRM exact 2027 vacation dates from the Aston MBChB timetable — most schemes run fixed 6–8 week blocks in late June–August and will not flex.
  - **Right to work:** CONFIRM. Pre-registration study in the UK does not by itself establish work rights, and several health-data schemes state "must have the right to work in the UK / we do not sponsor visas." This gates the Eligibility Gate in `04-job-evaluation.md`, so it must be settled before any application is drafted.
  - Birmingham-based during term; willing to relocate for a summer placement (the 2026 Nottingham internship is precedent). CONFIRM any geographic limits.

### Languages

| Language | Level | Notes |
|----------|-------|-------|
| English | Native / fluent | UK secondary and medical education; presented to clinical academics at the Royal College of Surgeons of England. |

<!-- CONFIRM: the CV declares no languages. Only English is recorded above, inferred
from UK medical study and UK conference presentation. Any other language the
candidate works in must be added by them - an undeclared language is a hard FAIL
in the Language Gate, so an omission here silently vetoes postings. -->

## Education

| Degree | Period | Institution | Key Topics |
|--------|--------|-------------|------------|
| MBChB, Bachelor of Medicine and Bachelor of Surgery | 2024 – expected 2029 | Aston University, Birmingham, UK | Health data science, digital health, evidence synthesis |

**Academic standing:** Merit awarded in both Year 1 and Year 2.

**Prizes and scholarships**
- **Jamila Hyatt Prize (2026)** — awarded for ranking first in Physiology and Pharmacology in Year 1.
- **HDR UK–Wellcome Biomedical Vacation Scholarship (2026)** — selected from 200+ applicants for one of six places.
- **HealthTech Foundations Scholar (2026)** — BiteLabs Digital Health × More than Medics.

## Professional Experience

### Research Intern, HDR UK–Wellcome Biomedical Vacation Scholarship — University of Nottingham, Biodiscovery Institute (June 2026 – August 2026)
Nottingham, United Kingdom
- Selected from 200+ applicants for one of six places on the scheme; placed on **TRExt**, a DARE UK–funded project converting clinical free-text into standardised **OMOP** data for use in Trusted Research Environments.
- Built **Lettuce Desktop**, a graphical interface for the project's open-source **LLM** mapping tool, letting researchers standardise clinical free-text to OMOP concepts locally, without coding, inside a secure environment.
- Coded the project's public-facing website in HTML (tre-text-analytics.github.io).
- Built a five-class **ECG classification pipeline** (PTB-XL, 16,000+ records) on the Helix HPC cluster, using **patient-disjoint folds** to prevent data leakage; best model reached **78% accuracy (macro-F1 0.65)**.

### HealthTech Foundations Scholar — BiteLabs Digital Health × More than Medics (Jan 2026 – Feb 2026)
United Kingdom
- Selected for a digital health innovation programme covering clinical problem definition, implementation, funding models, and alignment with clinical workflows.
- Co-developed and presented **WoundWatch** on final pitch day — a concept for AI-assisted wound monitoring in which patients submit images and symptom reports after discharge, supporting earlier detection of surgical site infections and safer recovery at home.

### Mentor — Medic Mentor Scholar; Zero Gravity Mentor (2024 – present)
United Kingdom
- Selected onto structured mentoring schemes supporting prospective and current students.

## Independent Projects

- **Lettuce Desktop** — desktop GUI for an open-source LLM-based clinical-concept mapping tool (OMOP standardisation) built during the Nottingham internship. CONFIRM whether this is public and linkable; a public repo is strong evidence for a health-data application.
- **tre-text-analytics.github.io** — project website, hand-coded in HTML.
- **Selected research projects** (see Publications / evidence synthesis below).

## Technical Skills

### Programming & ML
- **CONFIRM — no programming language is named anywhere on the supplied CV.** This is the single largest weakness in the CV for health-data-science screening: an ECG classification pipeline on an HPC cluster and a desktop GUI for an LLM tool both imply a concrete stack, but a recruiter or ATS keyword filter cannot credit a skill that is not written down. The candidate must confirm, with honest proficiency levels, which of the following they actually used:
  - Python, and which libraries (pandas / NumPy / scikit-learn / PyTorch / TensorFlow / wfdb)
  - R (common in health data science and evidence synthesis)
  - SQL
  - the Lettuce Desktop GUI framework (e.g. PyQt / Tkinter / Electron)
  - HPC / job-scheduler experience on Helix (e.g. Slurm)
  - Git / GitHub (a public GitHub profile exists, so some level is near-certain)
- **HTML** — coded the TRExt project website.
- **Machine learning (applied):** multi-class classification, cross-validation design with patient-disjoint folds to prevent data leakage, macro-F1 / accuracy evaluation.
- **NLP / LLM applications:** clinical free-text to OMOP concept mapping.

### Domain Expertise
- Health data science and digital health
- Clinical data standardisation — **OMOP** common data model; Trusted Research Environments (TREs)
- Evidence synthesis — systematic review, meta-analysis, meta-regression
- Clinical knowledge from MBChB study (physiology, pharmacology; first in year for both)
- Physiological signal data — ECG (PTB-XL)
- Stated interest: applications of data science and artificial intelligence in medicine

### Software & Tools
- Helix HPC cluster; Git/GitHub (CONFIRM level); HTML/web; systematic-review tooling (CONFIRM: Covidence / Rayyan / RevMan / EndNote and which meta-analysis software was used for the meta-regressions)

## Publications

Status as of the supplied CV — none yet in print; one manuscript under peer review and three conference presentations.

1. **Robotic-assisted versus laparoscopic appendectomy — systematic review and meta-analysis.** Co-authored with Yusuf Soliman and Kevin Felix; supervised by Sion Parry. Presented to clinical academics and surgeons at the **Surgical Research Society meeting, Royal College of Surgeons of England (January 2026)**; accepted for poster presentation in Athens (2026); **manuscript under peer review**.
2. **Prognostic utility of serum lactate dehydrogenase in brain metastases — systematic review, meta-analysis and meta-regression.** Accepted as an e-poster at **EANO 2026** (European Association of Neuro-Oncology congress), Rome, September 2026. Conducted with the Melanin Medics research division under the guidance of Dr Ikenna Ibeanusi.
3. **Prognostic utility of serum lactate dehydrogenase in primary malignant brain tumours — systematic review, meta-analysis and meta-regression.** Accepted as an e-poster at **EANO 2026**, Rome, September 2026. Conducted with the Melanin Medics research division under the guidance of Dr Ikenna Ibeanusi.

<!-- CONFIRM: whether the appendectomy manuscript has since been accepted or
published, and whether the two EANO abstracts appeared in a supplement with a
citable DOI. A published citation is worth materially more than "under review". -->

## Awards
- **Jamila Hyatt Prize** — Aston University, for ranking first in Physiology and Pharmacology in Year 1 (2026)
- **HDR UK–Wellcome Biomedical Vacation Scholarship** — 1 of 6 places from 200+ applicants (2026)
- **HealthTech Foundations Scholar** — BiteLabs Digital Health × More than Medics (2026)
- Merit, Year 1 and Year 2, MBChB, Aston University

## References

CONFIRM — no referees are recorded on the supplied CV. Strong candidates available from the
research record; the candidate must confirm each has agreed before any name is used:
- Nottingham/TRExt internship supervisor (name CONFIRM) — best referee for health data science specifically
- **Sion Parry** — supervisor, robotic vs. laparoscopic appendectomy review
- **Dr Ikenna Ibeanusi** — Melanin Medics research division, both LDH reviews

References available upon request.
