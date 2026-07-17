---
name: story-card
description: >-
  Use this skill whenever the user wants to write, draft, format, or refine a
  product story card, user story, backlog item, or Jira story/ticket. Trigger on
  phrases like "write a story", "draft a story card", "create a ticket", "turn
  this into a story", "spec this out", or whenever the user describes a product
  functionality they want captured as a work item for engineering — even if they
  never say the words "story card". This skill enforces one consistent format
  (title as "[Location] Functionality", a persona-based user story, design links,
  a summary, and acceptance criteria) and runs a short gap-analysis step that
  surfaces open questions and edge cases for the user to resolve BEFORE the card
  is written. Prefer this skill over free-form writing any time the output is a
  story for a backlog, so every card in the product looks and reads the same.
---

# Story Card Writer

## What this skill is for

The user is a product manager building functionalities under a product. They
want every story card to look and read the same so a person scanning the backlog
can understand any story at a glance. Your job is to take the user's context —
which may be richly detailed or just a few sentences — reason about it, surface
anything missing, and then produce a clean, readable, **functional** story card
in the exact format below.

The guiding philosophy, which should shape every decision you make:

- **Readable above all.** A story card is read far more often than it is written.
  Favor plain language and a clear structure over completeness-for-its-own-sake.
- **Functional, not technical.** Engineers will have a design, Figma, and/or a
  prototype to look at for the "how". The card describes how the feature should
  *behave* and the *edge cases* that matter — not implementation detail.
- **No arbitrary technical constraints.** Do not invent specifics like "the API
  must respond in under 1.5 seconds" or particular tech choices. They are noise.
  If something must be fast, say "should feel responsive" — not a made-up number.
- **Simple but complete.** Capture everything that genuinely affects behavior,
  and nothing that doesn't. When in doubt, leave it out and raise it as a
  question instead of padding the card.
- **Never repeat yourself.** Redundancy across sections is the enemy of
  readability. Each section earns its place by saying something the others don't.

## Grounding in this brain

Before writing, check the brain for context that should shape the card — don't
invent what's already decided:

- If the functionality maps to an existing capability, read its spec under
  `Modules/<Module>/<Capability>/` for scope, terminology, and prior decisions.
  **Specs are the source of truth; the story card is derived from them, not the
  other way around** — don't let the card contradict a spec.
- Check `Decisions/Decision-Log.md`; never write a card that contradicts a
  logged decision.
- Reuse the product's existing area vocabulary for the `[Location]` in the title
  (module/capability names as used in `Modules/`), not ad hoc labels.

## The workflow (do this before writing any card)

The user has been explicit that you should reason through their input and raise
gaps *before* writing, so they can answer or redirect. Do not skip this.

1. **Read and absorb the user's context.** Understand what functionality they're
   describing, who it's for, where it lives in the product, and what success
   looks like. Pull in the relevant spec (see "Grounding in this brain") if one
   exists.

2. **Analyze for gaps and edge cases.** Think about the unhappy paths and
   ambiguities a good engineer would hit: empty states, error states,
   permissions/roles, no-data or no-results, limits and boundaries, what happens
   on cancel/back, concurrent or repeated actions, and anything the user's
   description leaves genuinely undefined.

3. **Surface what you found — and separate two kinds of items:**
   - **Blocking questions** — things you genuinely cannot write a good card
     without. Ask these clearly.
   - **Recommendations / edge cases to consider** — behaviors worth deciding on,
     presented as suggestions the user can accept, reject, or amend.

   Present these concisely and let the user respond. The user may already know
   the answers, so asking is usually faster than guessing.

4. **Handle open questions deliberately.** Open questions are surfaced to the
   user for resolution — they do **not** go on the card by default. Only add an
   "Open questions" section to the card if the user explicitly says something
   like "add that as an open question." Otherwise resolve them in conversation
   and bake the answers into the card. Never silently assume an answer and write
   it onto the card as fact.

5. **Respect "just proceed".** If the user would rather not work through the
   questions ("just make a reasonable call", "proceed"), make sensible
   assumptions, **state those assumptions to the user in chat**, and write the
   card. Keep the assumptions in the conversation, not in the card.

6. **Write the card** in the exact format below.

## The title

The title is the single most important scanning aid, and it lives **only** as the
card/issue title — never repeat it inside the description body.

Default format:

```
[Location] Functionality
```

- **Location** (in brackets) is *where in the product* the functionality lives —
  the area, page, or module. Keep this from a consistent vocabulary: reuse the
  same label for the same area every time (e.g. always `[Dashboard]`, not
  sometimes `[Home]` and sometimes `[Main screen]`). Reuse the module/capability
  names as they appear under `Modules/` in this brain; if a new area comes up,
  pick a clear name and use it consistently. When unsure which label fits, ask.
- **Functionality** is a short, specific capability phrased so a reader instantly
  knows what the story is about — e.g. "Filter results by location radius",
  "Rename a saved report", "Bulk-export selected rows".

This format fits most stories. For the occasional story it doesn't suit (e.g.
cross-cutting work, a spike, tech debt), use the clearest title you can and don't
force the brackets — but treat that as the exception, not the rule.

## The card body — exact structure

Use this structure, in this order. Sections are separated by horizontal rules
exactly where shown. Every section uses the same bold-label format so the card
reads consistently top to bottom.

```
**User Story:** As a [persona], I want [capability] so that [outcome].

**Design:** [Figma link] · [prototype link]

---

**Summary:** One short paragraph of context — what we're building and why it
matters here. Add background the user story doesn't already give; do not restate
the "so that" benefit.

---

**Acceptance Criteria:**
[hybrid of brief framing text and bullets — see guidance below]

**Out of scope:** What this story explicitly does not cover. (Include only when
there's something worth fencing off.)
```

Notes on each section:

- **User Story** — Always include the persona ("As a ..."). Who the user is often
  changes the behavior and the edge cases, and it's cheap signal. If the user
  truly hasn't told you who it's for and it can't be inferred, ask rather than
  defaulting to a vague "user".
- **Design** — A place for the Figma link, the prototype link, or both. Check
  `Resources/Tooling-Map.md` for the relevant Figma file if one isn't given. If
  no link is available yet, write `TBD` so it's visibly pending rather than
  missing.
- **Summary** — One paragraph, same labeled format as the other sections. Its job
  is to add context (the *what* and any background), not to echo the user story.
- **Acceptance Criteria** — The heart of the card. See the dedicated guidance
  below. This is the single home for behavior, including edge cases — there is no
  separate "functional requirements" section and no separate "edge cases"
  section; folding them in keeps the card from repeating itself.
- **Out of scope** — Optional but high-value. One line drawing the boundary
  prevents over-building and scope creep. Omit the section entirely if there's
  genuinely nothing to fence off.
- **Open questions** — Do **not** include by default. Only add it (as a final
  section) when the user explicitly asks to park a question on the card.

## Writing acceptance criteria

Acceptance criteria define what "done" looks like in terms of observable
behavior. Aim for criteria a tester (or the PM) could actually check.

**Style — a readable hybrid.** Use short framing text where it helps orient the
reader, then bullets for the discrete, checkable criteria. Nested bullets are
fine when a criterion has sub-conditions. The goal is readability, so:

- Lead a bullet with a short **bold** phrase naming the behavior or scenario,
  then describe it in plain language. This lets a reader skim the bold lead-ins.
- Use formatting (bold, and occasionally <u>underline</u> for the one constraint
  that must not be missed) to *improve* scanning — but with restraint. The more
  everything is formatted, the less any of it stands out. Find the balance.
- Reserve a "When X, then Y" phrasing for genuinely conditional or edge-case
  behavior, where spelling out the trigger and the result adds clarity. Don't
  force every line into Given/When/Then — it makes simple criteria verbose.
- Fold edge cases in alongside the happy path: empty states, errors, no-results,
  permissions, limits, cancel/back behavior — whatever genuinely applies.

Keep criteria functional. "User sees a confirmation before the report is deleted"
is good. "DELETE endpoint returns 204" is implementation detail — leave it out.

## What to avoid

- Repeating the title inside the body, or repeating the user story's benefit in
  the summary.
- Invented non-functional numbers (response times, payload sizes, uptime) unless
  the user specifically provides a real requirement. When a non-functional
  concern genuinely matters (works on mobile, only admins can access, accessible
  to screen readers), express it as an acceptance criterion rather than a
  separate noisy section.
- Listing edge cases or requirements in their own section that duplicates the
  acceptance criteria.
- Putting unresolved open questions on the card without the user's say-so.

## Example

**Input from user (sparse):** "We need a way for users to rename their saved
reports. Right now they're stuck with whatever name they gave at creation."

**Good gap-surfacing before writing (in chat, not on the card):**
- Blocking: Who can rename — the report owner only, or anyone it's shared with?
- Consider: Should duplicate names be allowed? What's the max length? What
  happens if they clear the field and save an empty name?

**Resulting card after the user resolves those:**

```
Title: [Saved Reports] Rename a saved report

**User Story:** As a report owner, I want to rename one of my saved reports so
that its name stays meaningful as my analysis evolves.

**Design:** https://figma.com/file/... · TBD

---

**Summary:** Saved reports currently keep whatever name they were given at
creation, with no way to change it. This adds inline renaming from the saved
reports list so owners can keep their library organized over time.

---

**Acceptance Criteria:**
Renaming happens inline from the saved reports list, without opening the report.

- **Entering edit mode:** The owner can trigger rename from the report's row;
  the name becomes an editable field pre-filled with the current name.
- **Saving:** Confirming saves the new name and the list reflects it immediately.
- **Empty name:** <u>An empty name cannot be saved</u> — saving is blocked and the
  field shows a brief inline message until a name is provided.
- **Length:** Names longer than the allowed limit are prevented at entry rather
  than failing on save.
- **Cancel:** Pressing escape or clicking away discards the change and restores
  the original name.
- **Permissions:** When a user only has the report shared with them (not owner),
  the rename action is not available to them.

**Out of scope:** Renaming multiple reports at once; renaming from inside the
open report view.
```

Notice the title is not repeated in the body, edge cases live inside the
acceptance criteria, formatting is used sparingly to aid scanning, and there are
no invented technical constraints.

## Delivering the card

Produce the card as clean, copy-pasteable text in the format above. Then decide
where it goes based on the input:

- **Create it in Jira automatically when** the user mentions Jira (e.g. "make a
  Jira ticket", "add this to the board") **or** the input contains a Jira link
  (e.g. a story to relate it to, an epic, or a board URL). Default to the team's
  **delivery project** in `Resources/Tooling-Map.md` unless the user names a
  different one (e.g. the portfolio project for a customer-value epic, or another
  team's project). Use the connected Jira/Atlassian connector and map the
  `[Location] Functionality` title to the issue summary and the card body to the
  description. If a Jira link to an existing epic or story was given, link the
  new issue to it where it makes sense. After creating, share the new issue's
  link.
- **Otherwise, output text only** — just hand back the formatted card for the
  user to place wherever they want.

If Jira creation is expected but no project/issue-type is clear from the input,
ask which project (and issue type, if ambiguous) before creating.

⚠️ Creating or editing Jira issues is a write to a shared system others see —
confirm the destination (project, linked epic) with the user before creating,
per this brain's boundaries in `CLAUDE.md`.
