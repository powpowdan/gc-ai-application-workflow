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

## Step 1: what to install (from zero)

1. **git** and a **GitHub account**. git is version control software; get
   it from git-scm.com (or your operating system's package manager). The
   GitHub account is free: sign up at github.com.
2. **Node.js LTS** from nodejs.org, but ONLY if you pick a terminal agent
   in the next step: the terminal agents below install through npm, which
   comes with Node. If you pick a desktop agent, skip this step.
3. **One** AI coding agent. Any ONE of these runs this workflow:
   - opencode (the tool this system was built under):
     `curl -fsSL https://opencode.ai/install | bash`
     or `npm install -g opencode-ai`
   - Claude Code: `npm install -g @anthropic-ai/claude-code`
   - Cursor: a desktop app with its own installer from cursor.com
4. **First launch and sign-in**: launch your agent once, anywhere, and
   follow its sign-in steps. Every agent connects to an AI provider
   account (Anthropic, Google, OpenAI, or similar); some have free tiers,
   some need a subscription or API key. This is the only account setup
   the whole system requires.

   If you do not already have an AI provider account, these commonly have
   free access as of this writing (tiers change; check current pricing):

   - Google AI Studio (aistudio.google.com): free Gemini API key; works
     with most agents that let you pick a provider
   - OpenRouter (openrouter.ai): one key, many models, including
     free-tier ones
   - xAI (x.ai): the Grok API has offered trial credits; usable where
     your agent supports xAI

   Sign up, create an API key, and add it in your agent's provider
   settings (each agent documents this in its own setup guide).
5. That is everything. No other tooling is needed.

## Setup: clone to a PRIVATE copy (required, not optional)

This template repo is public. Your copy will contain your resume,
evidence map, and application history, so your copy must be private.
One-time setup:

1. `git clone https://github.com/powpowdan/gc-ai-application-workflow.git`
2. On github.com: New repository → name it → choose **Private** → create
   it EMPTY (no README, no license, nothing).
3. Point your clone at your new private repo:
   `git remote set-url origin https://github.com/<you>/<your-repo>.git`
4. `git push -u origin main`

NOTE: clicking **Fork** will not work: GitHub forks of public repos stay
public forever. Clone and push instead.

If git asks you to authenticate during the push, sign in when prompted
(browser sign-in on most setups, or a personal access token). SSH remotes
also work if you already have a key registered with GitHub; if you do not
know what that means, use the https URL.

Then open the folder in your agent. Most agents read `AGENTS.md`
automatically at session start. If yours does not, tell it: "read
AGENTS.md and follow it."

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

You do not have to fill these alone: the first-session prompts below let
the agent interview you to build them.

## Your first session: prompts to paste

In order. Each one assumes the previous is done.

1. Orientation (5 minutes, fills you in):

   > Read AGENTS.md and applying/AGENTS.md. Explain the workflow back to
   > me in plain language and tell me which files I must fill in before
   > my first application.

2. Build your evidence (the long one; do it in sittings):

   > Read applying/RESUME.md and applying/EVIDENCE-MAP.md, then interview
   > me to fill them: one skill claim at a time; ask me for the story,
   > the dates, and the numbers; never write a claim or a verb I cannot
   > defend for five minutes when probed.

3. Personal projects (if you have any independent work):

   > Read applying/PERSONAL-PROJECTS.md, then interview me about my
   > independent projects: for each one, ask what I built, with what
   > tools, what I did by hand versus directed an AI to do, and what
   > broke and how I fixed it. Assign honesty tiers (HAND or DIRECTED)
   > and verb ceilings I can defend for five minutes when probed.

4. Audit (completeness check before your first application):

   > Audit all my context files (RESUME, EVIDENCE-MAP, PERSONAL-PROJECTS,
   > ANSWER-BANK, PROCESS-LOG, old-screening-questions): list everything
   > still containing placeholders or "(example, replace)" rows, in
   > fill-priority order, and tell me the single cheapest next thing to
   > fill in.

5. Dry run (safe rehearsal, empty inbox):

   > Run the session-start check from applying/AGENTS.md. My INBOX is
   > empty; walk me through what will happen the day I drop my first
   > posting in.

6. Real run: save the posting text as `applying/INBOX/POSTING.md` and
   the screening questions as `applying/INBOX/QUESTIONS.md` (or paste
   them into chat), then:

   > Run the session-start check.

## Run it (every application after that)

1. Drop the posting text and screening questions into
   `applying/INBOX/` (as files, or paste them into chat).
2. Start a session. The workflow runs: intake, eligibility gate (area of
   selection, level logic, language, security, location, closing date),
   question-by-question feasibility grading (A/B/C/GAP), drafting in
   house style, then a three-pass authoring loop where YOU edit the
   drafts (pass 2), and the agent does the final hygiene pass.
3. You resolve the verify flags (dates, magnitudes, attributions) and
   submit. Outcomes get logged so answers improve over time.

The full pipeline definition is `applying/AGENTS.md`. The answer-writing
method is `applying/STAR-GUIDE.md`. Read both once yourself; you will
recognize the moments where the system asks you for a decision.

## Guardrails, built in and personal

Built into the workflow itself (you do not have to set these up, but
knowing they exist is why you can trust the system):

- The eligibility gate kills applications you cannot legitimately apply
  to BEFORE any work happens (wrong area of selection, level, language,
  security, location, closed deadline)
- The feasibility grading kills unanswerable applications: an essential
  question with no honest evidence (GAP) ends the process; a C-grade
  essential comes to you for a GO/NO-GO call with the full grade profile
  on the table
- Verb ceilings in EVIDENCE-MAP are absolute: the agent will not upgrade
  "supported" into "led" no matter how much better the draft would read
- Verify flags: every fact only you can confirm (dates, magnitudes,
  attributions) is flagged [ ] and left for you; the agent never resolves
  them by guessing
- Pass 2 of the three-pass loop is a human: you edit the drafts, and your
  edits override everything

Personal guardrails to hold yourself to:

- Never let the agent submit anything for you; you paste into GCjobs, you
  click submit
- Never skip pass 2; speed is how claims drift past evidence
- Commit after every pass: git is your undo button and your audit trail
- When the workflow says NO-GO or GAP, believe it; that is the system
  working, not failing

## What it will never do

- Invent facts, magnitudes, or attributions
- Upgrade a verb ceiling ("supported" becoming "led")
- Use a personal project where the poster's experience-source language
  does not allow it
- Draft an answer to an essential question it graded GAP (no honest
  evidence): the application dies instead
- Use em dashes (house style: commas, colons, semicolons, parentheses)
