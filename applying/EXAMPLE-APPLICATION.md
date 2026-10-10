# EXAMPLE APPLICATION (SYNTHETIC: read once, then ignore forever)

One full pass through the pipeline using the same fictional persona as
STAR-GUIDE §2 (a Lead Developer at [Department] who ships a high-traffic
policy publication under embargo). Everything below is invented to show
the SHAPE of a real application file: block order, grade reasoning, the
interview exchange, verify flags, and the reviewer simulation. Your real
applications live in `POSTINGS/<slug>/ANSWERS.md` per `POSTINGS/_TEMPLATE.md`.

Poster premise (synthetic): IT-02-equivalent Web Developer, area of
selection "persons employed across the public service," closing date
ahead, English Essential, Reliability clearance, experience sources:
work only (poster is silent on personal/academic).

## NOT pasted: gate verdict

- Eligibility: area of selection GO (public service-wide; applicant's
  substantive [classification] qualifies) / level logic GO (open
  process, applying down one level) / language GO (English Essential
  matches RESUME.md identity block) / security GO (Reliability held) /
  location GO / closing date ahead / operational requirements GO
  (occasional overtime confirmed acceptable by the applicant)
- Experience-source language: silent poster = work-only evidence for
  experience questions
- Feasibility grades: Q1=A, Q2=B (pre-interview; see below), AEX1=A
- Strategy: no essential below A after the grade-upgrade interview;
  asset drafted first (ranking fuel)

## NOT pasted: question routing and story allocation (this application)

| # | Question (exact wording) | Type | Route (EVIDENCE-MAP) | Grade | Anchor story |
|---|---|---|---|---|---|
| 1 | Describe your experience managing competing priorities to deliver a project under tight deadlines. | Essential | Tight deadlines row | A | Embargo release (STAR-GUIDE §2 persona) |
| 2 | Do you have experience designing and developing reports or dashboards to meet organizational reporting related requirements? | Essential | Data/reporting row | B → A after interview | Readership dashboard |
| AEX1 | Knowledge of web accessibility standards would be an asset. | Asset | Accessibility row | A | WCAG 2.2 AA enforcement on every changed page |

- Strongest-answer call: Q1 leads with the embargo story (deepest
  magnitude set); the dashboard anchors Q2; WCAG anchors AEX1
- Reserve for interviews: version-control adoption story (not used
  above; kept for interview probing)

## NOT pasted: grade-upgrade interview log (Q2, B at first grading)

Capping gap: missing magnitude (who reads the dashboard, how often,
what it replaced). Verb coverage was already honest (designed,
developed).

Round 1:
- Agent: "Who receives the dashboard output, how many people, how
  often, and what did it replace?"
- Applicant: "Monthly readership summary to the communications team and
  two directors, about 25 readers total. It replaced a manual report a
  senior analyst built by hand every month, roughly half a day of
  work."
- Outcome: magnitude gained (25 readers, ~4 hours saved monthly). Grade
  B → A. New facts recorded into EVIDENCE-MAP magnitudes list.
- Agent: "Is there a second dashboard example at another team for
  breadth?"
- Applicant: "No, only this one; anything older is too dated to cite."
- Outcome: no new usable evidence from this probe.

Round 2:
- Agent: "Does anyone track usage of the dashboard itself?"
- Applicant: "Not tracked. Nothing more to add."
- Outcome: no new usable evidence; grade already at A, ceiling
  confirmed. STOP per the stop conditions (grade reached A; further
  probing would be interviewing past an honest ceiling).

## Q1. Describe your experience managing competing priorities to
deliver a project under tight deadlines.

Yes, I have experience managing competing priorities and delivering
under tight deadlines, as Lead Developer ([classification]) at
[Department] (MM/YYYY to Present).

(S) During the 2024 release of a high-traffic policy publication at
[Department], last-minute content changes required urgent website
updates hours before publication under a strict embargo. (T) As Lead
Developer, I was responsible for implementing and verifying
rapid-response code changes without breaking live content. (A) I
implemented the HTML/CSS/JS updates, ran structural and accessibility
(WCAG 2.2 AA) verification on every changed page, coordinated directly
with the requesting office to confirm content priorities when competing
changes arrived together, and used our Git workflow to stage and safely
roll back changes. (R) All updates deployed error-free and on schedule;
across four release cycles as Lead, the site sustained peak traffic
with zero downtime.

### NOT pasted: verify flags

- [ ] "four release cycles" count accurate for the applicant
- [ ] "zero downtime" defensible under probe
- [ ] 2024 release date correct
- Chars: ~810/1500 (intro sentence excluded)

## Q2. (drafted at A after the interview; same structure as Q1)

Intro sentence mirrors the question; STAR body leads with the dashboard
story including the magnitude gained in the interview (25 readers, ~4
hours saved monthly); verify flag on the "half a day" estimate only.

## NOT pasted: reviewer simulation (pass 3)

Q1, per component of the wording:
- "managing competing priorities" → MEETS (competing changes
  prioritized with the requesting office, stated in sentence 1 and A)
- "deliver a project" → MEETS (concrete project, four cycles)
- "under tight deadlines" → MEETS (hours before publication, embargo)
- Result with observable fact → present (zero downtime, four cycles)
- 30-second skim test: mirror sentence first, magnitude present →
  a non-technical screener checks MEETS

Q2: all components MEETS; magnitude present. AEX1: MEETS.
Verdict: file goes to pass 2 (the applicant), no answer returned for
rework.

## Footer

- Persona is fictional and shared with STAR-GUIDE §2 so the two
  documents reinforce each other
- Once you have one real POSTINGS/ folder, this file has no further
  use; keep it for the next rookie or delete it
