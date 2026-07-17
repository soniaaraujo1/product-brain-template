---
name: onboard-brain
description: Set up a fresh copy of the product-brain template for a new product. Interviews the owner about the product, team, personas, and tool stack, fills every {{placeholder}}, seeds the module structure, optionally imports existing docs, and verifies nothing is left unfilled. Use on the first run in a new brain, when the user says "set up this brain", "onboard my product", "make this brain mine", or whenever CLAUDE.md still contains {{…}} placeholders.
---

# Onboard this brain

Take a fresh copy of the product-brain template and turn it into a working brain for one product,
in one guided session. You interview; the owner answers; you write.

## Before starting

1. **Check it's actually fresh.** Grep the repo for `{{`. If nothing is found, the brain is already
   onboarded — say so and stop (offer to update specific files instead).
2. **Confirm who you're talking to.** The person onboarding becomes the brain's owner (the only
   person who writes to it, per `CLAUDE.md`). Confirm name, role, and email.
3. **Ask what already exists.** If the owner has material lying around (a PRD, a decision list, a
   roadmap deck, meeting notes, an old wiki page), note it now — importing it is the last step and
   it makes the brain useful on day one.

## The interview — three short passes

Ask in passes, not one 20-question wall. Propose defaults where you can infer them (from anything
the owner pasted, from the repo name, from earlier answers); the owner confirms or corrects. Never
leave a placeholder filled with a guess.

**Pass 1 — Identity**
- Product name (and short form, if any). One sentence: what it is and for whom.
- Owner: name, role, email. Company/org.
- Where the repo will be hosted (URL, or "TBD").

**Pass 2 — Product shape**
- The modules / major areas of the product (name + one line + status each).
- Personas: the primary one (role, job-to-be-done, pains) and any secondary ones.
- Where things stand: the current release or main bet, roughly what's next.
- The 1-3 decisions already made that everyone must respect (they become the first ADRs).
- Any domain terms that need pinning down (they seed the Glossary).

**Pass 3 — Tool stack**
- Where delivery work is tracked: Jira project key(s), or whatever the org uses (Linear, Azure
  DevOps, …). One project is **the default destination for story cards**.
- Where roadmap/portfolio epics live, if anywhere (a portfolio Jira project, a slide, a doc).
- Docs/wiki space (Confluence or equivalent), design files (Figma or equivalent), a story map if
  one exists — names + links.
- Anything else work ships into.

**If the org isn't on Jira/Confluence/Figma:** the structure works unchanged; only the execution
edges shift. Record the real tools in the Tooling Map, and flag that `story-card` (delivery
tickets) and `roadmap-card` (portfolio epics) assume a Jira-style connector — their card formats
still apply, but the "write to tool" step needs adapting to the org's stack. Note this in
`To-Do.md` so it isn't forgotten.

## Writing pass — fill the brain

With answers in hand, update these files (and only these; the rest of the template stands):

1. **`CLAUDE.md`** — replace every `{{…}}`: product name, owner name/role, tools summary line.
2. **`README.md`** — replace the template pitch: keep the "why / four layers / how to use /
   conventions" content, retitle it for the product, drop the "adopt it in three steps" section
   (it has served its purpose), and set the real repo URL.
3. **`Overview.md`** — write it properly from the Pass 1-2 answers; this is the orientation file,
   make it read well, not like a filled form.
4. **`Resources/Tooling-Map.md`** — the real tool table from Pass 3. Remove rows that don't
   apply; rename sections if the org uses different tools.
5. **`Resources/Personas.md`** — one section per persona, primary marked.
6. **`Resources/Team.md`** — owner + any teammates named.
7. **`Resources/Glossary.md`** — seed any terms from Pass 2.
8. **`Roadmap/README.md`** — owner, date, and whatever Now/Next/Later content the owner gave;
   leave empty tables where nothing is known yet.
9. **`Modules/<Module>/README.md`** — seed one per named module from `Modules/_templates/module.md`
   (top-level README only; capabilities come later). Update the index in `Modules/README.md`.
10. **First ADRs** — if Pass 2 surfaced already-made decisions, log each with
    `Decisions/_TEMPLATE.md` plus a row in `Decision-Log.md`.

Date-stamp what you write (use today's date, not placeholders).

## Verify, then hand over

1. **No placeholder left behind:** grep the repo for `{{` again — it must return nothing.
2. **Links resolve:** the files you wrote link to each other relatively; spot-check that the paths
   you created actually exist.
3. **Portfolio fields:** if the org tracks roadmap epics in Jira, note that
   `roadmap-card/references/portfolio-fields.md` fills itself in on the first `/roadmap-card` run
   (field discovery); nothing to do now.
4. **Import what exists** (if the owner flagged material in "Before starting"): meeting notes and
   transcripts via `/capture-meeting`; an existing PRD or spec into `Modules/…` via the templates;
   known competitors as stubs in `Competitive-Intel/`; loose follow-ups into `To-Do.md`. Route,
   don't dump.
5. **Close the loop:** suggest committing and pushing, having the team clone it, and running
   `/capture-meeting` on the next meeting so the habit starts immediately.

## Guardrails

- Don't invent modules, personas, decisions, or links. Unknown is a fine answer; leave the
  template's empty structure in place and say what's still open.
- Don't restructure the template (folders, rules, routing) during onboarding; it's deliberately
  uniform. Product-specific conventions can be added to `CLAUDE.md` later.
- Everything stays local until the owner pushes; don't create Jira/Confluence artifacts during
  onboarding.
