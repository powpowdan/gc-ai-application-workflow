# applying/AGENTS.md: GC application workflow

Read when doing application work (postings, screening questions, resumes,
interviews). Raw drops land in `INBOX/`; one folder per application under
POSTINGS/.

## Context files, in read order

1. `RESUME.md`: canonical titles, orgs, dates, claims
2. `EVIDENCE-MAP.md`: claim→backing routing; verb ceilings are ABSOLUTE;
   magnitudes list (facts only the applicant knows: ask, never fill by
   guessing)
3. `PERSONAL-PROJECTS.md`: personal evidence + honesty tiers (HAND/DIRECTED)
4. `ANSWER-BANK.md`: reusable answers, observed phrasings, usage/outcome log
5. `old-screening-questions.md`: real observed question formats + the
   applicant's accumulated answers (mine these for format, not for claims;
   some early answers get corrected later as evidence is rechecked.
   EVIDENCE-MAP wins conflicts)
6. `STAR-GUIDE.md`: method; reread §3 and §6 before drafting anything

## Workflow: new posting

0. SESSION-START CHECK: the FIRST action of any applying session is to
   check `INBOX/`. Non-empty means intake and the eligibility gate (step 2)
   run before any other session work, including evidence prep, context-file
   updates, or question reading (lesson from a 2026 process: evidence prep
   was done for two postings that then failed the gate on area of
   selection)
1. Intake: the applicant drops POSTING + QUESTIONS files into `INBOX/` or
   pastes them into chat. Empty INBOX = nothing awaiting processing;
   process INBOX to empty before ending a session
2. ELIGIBILITY GATE (kill fast, before any work):
   - Who can apply (area of selection): public-wide, all public service
     employees, department-only, or AT-LEVEL only? If internal/at-level/
     group-restricted, check whether the applicant's current substantive
     position qualifies. Classification-group equivalence questions (for
     example, IS vs IT groups) are genuinely ambiguous; when unclear,
     email the poster's HR contact BEFORE drafting (they answer these
     routinely) and wait for the answer; the applicant decides with that
     information
   - Level logic: open/public processes generally allow applying down one
     level from a substantive classification; internal at-level processes
     do not
   - Hard requirements sweep: closing date not passed; language profile
     (bilingual imperative requires testing: confirm what the applicant
     holds); security level vs what the applicant holds; location/hybrid
     vs where the applicant can work; education requirements vs the
     applicant's credentials; operational requirements (overtime/on-call:
     only the applicant can answer these)
   - Verdict: GO proceeds. NO-GO gets a PROCESS-LOG row (Stage: outcome)
     with the disqualifier, no POSTINGS folder, and raw files moved to
     `POSTINGS/_archive/`. AMBIGUOUS means ask HR and wait
3. QUESTION FEASIBILITY SCAN (graded): route every question against
   EVIDENCE-MAP before drafting anything, then grade the strongest honest
   answer each question can support:
   - A (strong): WORK-backed story at/above the poster's needed verb
     level, STAR-complete, magnitudes known or fillable
   - B (adequate): honest evidence at defensible verbs but thinner:
     smaller scope, magnitude gaps needing verify flags
   - C (stretch): defensible only at low verbs or narrow scope; survives
     a 5-minute spoken defense but loses to a strong field
   - GAP: no honest evidence at any defensible verb level
   Decision rules:
   - Essential question at GAP = the application dies: no drafting, no
     stretching, no invention. One GAP on an essential is fatal
   - Essential question at C = GO/NO-GO goes to the applicant with the
     full grade profile on the table; a C-heavy application usually is
     not worth the lead time
   - Asset questions never kill an application, but grade them too:
     A-assets get drafted first (ranking fuel), C-assets are the first
     candidates to answer No
   - Record the grade profile in the ANSWERS.md routing block (NOT
     pasted) and summarize it in the PROCESS-LOG row, same as
     disqualifiers, so patterns stay visible across processes
4. Create `POSTINGS/<slug>/`, move files in as POSTING.md + QUESTIONS.md, add
   a PROCESS-LOG row. Slug rule: `<dept-short>-<poster#-tail>-<level>`
   (e.g., esdc-205123-it-02). Unique per process so concurrent
   same-department postings never collide. Track current state in the
   PROCESS-LOG Stage column (inbox / gate / drafting / pass-2 / ready /
   submitted / outcome); update it at every transition
5. Extract from the poster:
   - Qualification table: type (essential/asset), EXACT wording, char limits
   - Experience-source language (personal/academic allowed? quote it)
   - Any poster-specific mandatory answer format (e.g., Organization /
     Position & Duration / Details)
   - The application FORM's instructions, not just the poster: date format
     (e.g., MM AAAA to MM AAAA), actual char limits, any "Important
     messages" block. Ask the applicant to copy these from the live form
     BEFORE drafting (lesson from a 2026 process: the form and the poster
     differ)
5.5 Evidence refresh: ask the applicant "any new work, assignments,
   projects, or numbers since the last application?" (lesson from a 2026
   process: a new assignment surfaced mid-draft, not at intake)
6. Route each question via the EVIDENCE-MAP quick-routing table; check
   ANSWER-BANK for proven material first; de-conflict stories: one strong
   example anchors ONE answer per application; keep the rest in reserve for
   interview stages (note the allocation in the ANSWERS.md file). If the
   poster lists ASSET qualifications, pre-draft those answers too, even if
   the QUESTIONS file omits them; they are ranking fuel and need MORE lead
   time when evidence is thin (lesson from a 2026 process: an asset
   question was unprepared at the deadline)
   - Concurrent postings: each posting gets its own full gate and a fresh
     format/limit re-check even when questions look identical to a previous
     application. Reuse answers across applications freely, but re-verify
     char limits, date formats, and experience-source language each time
     (one 2026 poster allowed personal/academic sources; a silent poster
     forces rework to work-only evidence)
7. Draft ANSWERS.md, one section per question, structure per
   `POSTINGS/_TEMPLATE.md` (gate verdict + routing/allocation blocks
   marked NOT pasted, then answer sections):
   - Standard intro sentence: "Yes, I have [mirror the question's
     wording], as [current title] ([classification]) at [current
     department] (MM/YYYY to Present) and previously as [previous title]
     ([classification]) at [previous department] (MM/YYYY to MM/YYYY)."
     Current role first, exact dates. If the poster specifies a date
     format (e.g., "MM AAAA to MM AAAA"), match it; default to MM/YYYY
     when unspecified. Day-level precision lives in the not-pasted
     Position reference block only. Stories acquired in a previous role
     use the "...acquired as [previous title] at [previous department]...;
     I am now [current title] at [current department]..." variant
   - Bodies ≤1,500 chars; intro sentence excluded from char counts
   - Hands-on IT register (develop, test, deploy, troubleshoot), not
     managerial verbs; tools-first framing (the tools ARE the digital
     solutions); steer away from job framing that obscures the hands-on
     IT work
   - STAR: a result sentence in EVERY answer; run the STAR pre-submission
     checklist after EVERY revision, not just the first draft
   - Verify flags [ ] on every fact only the applicant can confirm (dates,
     magnitudes, attributions); never resolve them by guessing
   - Where the experience source spans orgs: attribute to the current role
     where evidence genuinely exists there; otherwise state the acquiring org
     honestly
8. Three-pass authoring (lesson from a 2026 process: iterating alone
   against the applicant's taste wasted four rounds):
   - Pass 1 (agent): draft in house style from the start
   - Pass 2 (applicant): substance/style edits and inline notes in ALL
     CAPS or parentheses; those edits override the draft
   - Pass 3 (agent): hygiene pass: typos, STAR checklist, char counts,
     verify-flag resolution, em-dash sweep, org prefixes on every
     paragraph; apply notes and remove them
9. The applicant verifies flags → submit → fill Applied date in
   PROCESS-LOG and set Stage to submitted
10. On outcome (screened in/out, interview, pool): mark affected ANSWER-BANK
    entries with the result and refine; fill post-submission notes; set
    Stage to outcome

## House style (lessons from 2026 rewrites)

- Current role ALWAYS first in the intro sentence, even when the story was
  acquired in a previous role: "acquired as [previous title] at [previous
  department] (dates) and as/previously [title] at [department] (dates)".
  All sources (academic, independent) go in the same sentence, current
  role leading
- Definition-matching: read the poster's own definition of key terms
  (e.g., "digital solutions = software applications, software services,
  low-code solutions, or data products") and cover the definition's edges
  with a breadth paragraph pairing the lead story with a second example
  plus current-role work. Defend against the strict reviewer, not just
  mirror the question
- Professional IT nouns (access-control rules, role-based security groups,
  governed, high-availability, WCAG standards) while verbs stay hands-on
  (develop, configure, troubleshoot, deploy)
- Two-paragraph body shape: paragraph 1 = strongest story detail; paragraph
  2 = breadth across orgs, ending on the current role
- Never self-undercut in pasted text ("I only watched", "assisted with"):
  honesty lives in verb choice (collaborate, support, partner), never in
  disclaimers
- No unexplained acronyms: expand on first use (e.g., RDS = Amazon's
  managed relational database service)
- Planning notes/WHY blocks stay in the file marked "NOT pasted", never in
  the answer text; run a typo + STAR pass after every edit

## Hard rules

- Verb ceilings in EVIDENCE-MAP are absolute; never upgrade them
- Never use em dashes in any writing, including answers. Use commas,
  colons, semicolons, periods, or parentheses instead
- Never invent facts, magnitudes, or attributions. Reference checks and
  interview probes are real; every claim must survive a 5-minute spoken
  defense (STAR-GUIDE rule 8)
- If the applicant proposes a claim the record contradicts, surface the
  conflict with the source and let THEM decide: their memory overrides old
  documents, but say what the record showed
- The inverse happens too: the applicant under-claims below the record.
  Surface the record and reconfirm before drafting on the lower
  self-assessment
- Personal-project evidence only where the poster's source language allows
- Asset questions get full STAR treatment too; they are ranking fuel
- Story reuse ACROSS applications is fine; within one application, never
