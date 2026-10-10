# GC Application Workflow

A context-file-driven workflow for Government of Canada job applications
(postings, screening questions, resumes, interviews), run by you plus an
AI coding agent. The agent follows the instructions in `AGENTS.md`; you
supply the judgment, the memory, and the facts. The system's core promise:
it will never invent a claim, upgrade a verb beyond your evidence, or fill
in a number only you can confirm.

In the workflow documents, "the applicant" means you.

## What this is not

This is not a resume generator. It is an evidence-discipline system: every
answer it drafts is routed from your own evidence map, graded for honesty,
and verified by you before submission. Bad evidence produces a "do not
apply" verdict, not a stretched answer.

## Step 1: what to install

1. **git** and a GitHub account (you were invited as a collaborator on
   this repo; clone it).
2. **One** AI coding agent that reads `AGENTS.md` files. Any of the
   common ones work: opencode, Claude Code, Cursor, Gemini CLI, and
   similar. Nothing else is required; no other tooling is needed.

## Setup

1. `git clone <this repo's URL>` and open the folder in your agent.
2. Most agents read `AGENTS.md` automatically at session start. If yours
   does not, tell it: "read AGENTS.md and follow it."

## Make it yours (one evening of work, in this order)

All files live under `applying/`. Templates contain synthetic example rows
marked "(example, replace)"; delete those as you fill in real content.

1. `applying/RESUME.md`: your canonical titles, orgs, dates, and claims.
   This is the record of record; the agent treats it as truth about your
   history.
2. `applying/EVIDENCE-MAP.md`: the heart of the system. For every skill
   claim you might make in an answer: what backs it (work, personal,
   academic), the strongest verb you can honestly use (the "verb
   ceiling"), and the story to cite. Also the magnitudes list: numbers
   only you know, which the agent must ask you for, never guess.
3. `applying/PERSONAL-PROJECTS.md`: your independent work, with honesty
   tiers (code you wrote by hand vs. work you directed and verified).
4. `applying/old-screening-questions.md`: a catalog of real observed
   question formats. Add every question you encounter; it teaches the
   agent the phrasing patterns screeners use.
5. `applying/ANSWER-BANK.md` and `applying/PROCESS-LOG.md`: start from
   the skeletons; they grow with use.

## Run it

1. Drop the posting text and screening questions into
   `applying/INBOX/` (as files, or paste them into chat).
2. Start a session with your agent. The workflow runs: intake, eligibility
   gate (area of selection, level logic, language, security, location,
   closing date), question-by-question feasibility grading (A/B/C/GAP),
   drafting in house style, then a three-pass authoring loop where YOU
   edit the drafts (pass 2), and the agent does the final hygiene pass.
3. You resolve the verify flags (dates, magnitudes, attributions) and
   submit. Outcomes get logged so answers improve over time.

The full pipeline definition is `applying/AGENTS.md`. The answer-writing
method is `applying/STAR-GUIDE.md`. Read both once yourself; you will
recognize the moments where the system asks you for a decision.

## What it will never do

- Invent facts, magnitudes, or attributions
- Upgrade a verb ceiling ("supported" becoming "led")
- Use a personal project where the poster's experience-source language
  does not allow it
- Draft an answer to an essential question it graded GAP (no honest
  evidence): the application dies instead
- Use em dashes (house style: commas, colons, semicolons, parentheses)
