---
name: roadmap-card
description: >-
  Use this skill whenever the user wants to create, draft, or refine an epic or
  initiative on the roadmap (the portfolio-level Jira project): a major product
  launch, deployment, or cross-team bet at the portfolio level. Trigger on
  phrases like "create a roadmap epic", "new initiative", "add this to the
  roadmap", "make a roadmap card", "spin up an initiative for X", "put this
  launch on the roadmap", or whenever the user describes a product launch or
  large program they want tracked as a roadmap card, even if they never say the
  words "epic" or "initiative". This is for roadmap-level, customer-value epics
  and initiatives in the portfolio project, not individual feature stories (use
  story-card for a single feature or functionality in the team's delivery
  project). It enforces one consistent card format (title, a business and user
  value proposition, a Problem / Solution / Scope description, and the portfolio
  classifier fields) and interviews the user to fill gaps and validate every
  assumption BEFORE writing anything to Jira.
---

# Roadmap Card Builder

## What this skill is for

The user is the PM who owns this product's roadmap. The portfolio Jira project
(see `Resources/Tooling-Map.md`) is the board where major product launches,
deployments, and bets live as **epics** or **initiatives**. The user wants every
roadmap card to look and read the same, so anyone scanning the board understands
the value, the problem, and the scope at a glance.

Your job: take the user's context (which may be a full brief or a few sentences),
reason about it as a product manager would, act as a critic that surfaces what is
missing, guide the user through the fields they have not filled in yet, and then
produce one clean, consistent card and write it to the right portfolio fields,
only after the user has approved it.

## Guiding philosophy

- **Readable above all.** A roadmap card is read by many people who are not close
  to the work: other PMs, leadership, delivery leads. Favor plain language and a
  clear structure over completeness for its own sake.
- **Formatting is restrained.** Only **bold** and bullet points. No headings with
  `#`, no tables, no italics-for-emphasis noise. Bold is for section labels and
  for the lead-in of a bullet. That is the whole toolkit.
- **No em dashes.** They read as machine-written. Use commas, parentheses,
  colons, or two sentences instead. This applies to every field you write.
- **Sourced, never invented.** Do not invent numbers, dates, customer names,
  team commitments, or scope. Ground the card in the brain and in what the user
  tells you. If you do not know something, ask or mark it as open, never fill it
  with a plausible guess.
- **Value first.** The value proposition is the heart of a roadmap card. Get it
  sharp before worrying about the mechanics.

## Epic or Initiative: choose deliberately

- **Initiative** = a larger program that spans multiple teams, multiple epics,
  and usually multiple releases (for example "<Module> (GA)"). It is the parent
  that groups build epics.
- **Epic** = one deliverable or release worth of customer value that can sit
  under an initiative (for example "<Module> MVP (Release 1)").

If the portfolio project only has one level (epics, no initiatives), collapse to
that and skip the parent question. If it is not obvious from the scope which one
the user means, ask. When creating an epic, expect it to have a parent
initiative and help find it (see `references/portfolio-fields.md`). Do not guess
the parent.

## Grounding in this brain

Before writing, pull the context that should shape the card. Do not reinvent what
is already decided or specced.

- If the work maps to a module or capability, read its spec under
  `Modules/<Module>/<Capability>/` for scope, terminology, and prior decisions.
- Read the relevant `Roadmap/` files (`README.md` for the portfolio view, the
  `<Initiative>.md` files, the release files) so the card fits the existing program
  and you can set the parent and release correctly.
- Check `Decisions/Decision-Log.md`; never write a card that contradicts a logged
  decision.
- For the value proposition and competitive stance, `Competitive-Intel/` and the
  capability specs are useful evidence. `Resources/Tooling-Map.md` has the Figma
  files and Jira links.

Reuse the product's existing vocabulary (module and capability names as they
appear under `Modules/`), not ad hoc labels.

## The workflow: interview and criticize before writing

The user has been explicit: **do not assume, and do not expect everything in one
go.** Guide them through the card, proposing what you can and asking for what you
cannot determine. Never write an assumed value onto the card as if it were fact.

1. **Absorb the context.** Understand what is being launched or built, who it is
   for, the business case, where it sits on the roadmap, and what release it
   targets. Pull in the brain grounding above.

2. **Draft what you can, flag what you cannot.** Work through the card in this
   order, filling what the context supports and marking the rest:
   - Title
   - Value proposition (business value, user value, or both)
   - Description (Problem, Solution, Scope of work)
   - Classifier fields (whatever the portfolio project defines — owning team,
     investment type, competitive positioning, or similar)
   - Priority, Release, Parent
   - Design and spec/PRD links

3. **Act as a critic and surface gaps, split into two kinds:**
   - **Blocking questions**: things you genuinely cannot write a good card
     without (for example: what problem does this actually solve, who is the user,
     is this an epic or an initiative). Ask these plainly.
   - **Proposals to confirm**: for the classifier fields and the parent and
     release, propose a value with a one-line rationale and let the user accept,
     change, or reject it. This is where you earn your keep as a PM: recommend,
     do not interrogate.

   Present these concisely so the user can answer in one pass. It is normal for
   the user to add information across several turns; keep track of what is still
   missing and keep guiding them until the card is complete.

4. **State assumptions out loud.** If you have to make a judgement call, say so in
   chat before writing so the user can correct it. Assumptions live in the
   conversation, never silently on the card.

5. **Handle "just proceed".** If the user says to make reasonable calls and go,
   make sensible choices, state them in chat, and continue to the draft. Still
   show the draft before writing to Jira.

6. **Show the full draft, get approval, then write.** Present the complete card
   (every field, mapped) as text in chat. Only after the user approves do you
   create or update the Jira issue. Nothing reaches the portfolio board
   unvalidated.

## The card format

### Title (Summary)

A short noun phrase naming the thing and its stage. Follow the house pattern:
`<Module or product>: <what it is>` or `<Module> (<stage>)`. Examples:
`<Module> (GA)`, `<Module> MVP (Release 1)`. Keep it scannable; do not restate it
inside the description.

### Value Proposition

A short, sharp statement of the value. If the portfolio project has a dedicated
value-proposition field, it goes there; otherwise lead the description with it.
Cover **business value, user value, or both**, depending on what the initiative
actually delivers. Label each side that applies with a bold lead-in; include
only the sides that are real.

Both sides apply:

```
**For the business:** <one or two sentences on revenue, retention, differentiation, cost, or strategic position>
**For users:** <one or two sentences on the job it lets them do better, faster, or for the first time>
```

Only one side applies: write just that one labeled paragraph. Do not manufacture
the other side to look balanced. If a side has more than one distinct strand, a
short bulleted list with bold lead-ins is acceptable, but prefer the tight
labeled paragraph.

Keep it evidence-based. The value should follow from the problem in the
description, not from adjectives.

### Description

The description field carries three sections, in this order, each with a bold
label and each closed by a horizontal rule (`---`) so the sections read as
distinct blocks. Keep each tight.

```
**Problem**

<What is broken, missing, or costing us today, and for whom. Ground it in real
symptoms, not abstractions. One paragraph.>

---

**Solution**

<What we are building or launching and how it addresses the problem. One
paragraph; use bullets for the distinct moving parts if it reads better.>

---

**Scope of work**

* <What is included in this epic or initiative>
* <...>

---
```

Notes:
- **Problem** and **Solution** are prose. **Scope of work** is usually bullets.
- A `---` divider closes each section, including the last, matching the house
  style used on story cards.
- If the user gives you clear out-of-scope boundaries or specific asks of teams
  (engineering, data science, design), fold them into Scope of work as bullets.
  Do not add separate sections for them unless the user asks; the standard is
  these three labels.
- No `#` headings. The bold label is the header.

### The other fields

Every portfolio project defines its own classifiers. Read
`references/portfolio-fields.md` before mapping fields or writing; on first use
it tells you how to discover the project's real fields and record them there.
Common ones, and how to propose values (always with a one-line rationale, then
confirm):

- **Owning team / squad:** the team that owns delivery. Usually this product's
  team (see `Resources/Tooling-Map.md`).
- **Investment type** (if the org classifies bets): e.g. innovation vs. core
  strategy vs. technical debt. Tie the choice to the problem and the bet.
- **Competitive positioning** (if used): parity vs. differentiation. Use
  `Competitive-Intel/` as evidence where relevant.
- **Priority:** propose based on the roadmap context; default Medium if unclear.
- **Release (Fix version):** fetch the current allowed values live (they change
  often); do not invent a version name.
- **Parent:** for an epic, the initiative it belongs under. Find and confirm it.
- **Design and spec/PRD links:** URLs if available; otherwise leave blank and
  note it as pending rather than inventing a link.

## Writing to Jira

Read `references/portfolio-fields.md` for the mechanics (field discovery, custom
field IDs, rich-text/ADF handling, fetching releases live, finding the parent).

Writing to the portfolio board is a change others will see. Confirm the
destination (issue type, parent, release) with the user as part of the approval
step, per the boundaries in `CLAUDE.md`. After creating, share the new issue link
and capture the key back into `Roadmap/`.

If the org does not track roadmap epics in Jira at all, deliver the card as
clean text for wherever the roadmap lives, and file it in `Roadmap/` (the
initiative or release file) so the brain stays the source of truth.

## Example

**Input from user (sparse):** "Let's put the Insights relaunch on the roadmap.
It's the old legacy product, we're bringing it into the new platform. I think
it's an epic under an Insights initiative eventually, but for now just the
relaunch. Our squad owns it."

**Good critic pass before writing (in chat, not on the card):**
- Blocking: What is the core problem the relaunch solves for users today (dated
  experience, missing from the new platform, lost customers)? What does the
  relaunch actually include versus the legacy product?
- Blocking: Epic or initiative? You said epic "for now"; is there a parent
  initiative to link, or should this stand alone until one exists?
- Proposals to confirm: Investment type `Core strategy` (carrying a legacy
  product forward), Competitive positioning `Parity` (matching what the market
  expects), Priority `Medium`, owning team per the Tooling Map. Release: which
  train are you targeting? Design / PRD links if any.

**Resulting card after the user resolves those:**

```
Type: Epic    Project: <portfolio key>    Parent: <initiative or none>

Title: Insights: relaunch on the new platform

Value Proposition:
**For the business:** Brings an acquired legacy product onto the current
platform, protecting the renewals that still depend on it and closing a gap in the
consolidated offering.
**For users:** Restores Insights for existing customers inside the new
experience, so they keep the analysis they rely on without dropping back to the
legacy tool.

Description:
**Problem**

Insights lives only in the legacy product, outside the new platform. Customers
who value it are stranded between two experiences, and the gap weakens the case
for consolidating onto one platform.

---

**Solution**

Relaunch Insights natively in the new platform, matching the analysis customers
already use, so it stands alongside the other modules under one experience and
one set of filters.

---

**Scope of work**

* Port the core Insights views into the new platform
* Reuse the platform's shared filtering and context model
* Confirm data coverage matches what legacy customers expect

---

Owning team: <squad>
Investment type: Core strategy
Competitive positioning: Parity
Priority: Medium
Release: <confirmed train>
```

Notice: only bold and bullets, no em dashes, value split into the two sides that
genuinely apply, description limited to Problem / Solution / Scope, and every
classifier proposed with a rationale rather than assumed.
