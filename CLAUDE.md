# {{PRODUCT}} — Product Brain · agent guide

Routing + rules for working in this brain. **Read this, then load only the file(s) the task needs.**
After doing work, write durable facts back to the right folder (see the map).

> **⚡ Not onboarded yet:** if this file still contains `{{…}}` placeholders, this brain is a fresh
> copy of the template. Before doing anything else, offer to run `/onboard-brain` to set it up for
> the user's product. Don't produce product content against unfilled placeholders.

## Routing map — read what the task needs, nothing more

| If the task is about… | Go to |
|---|---|
| What the product is (orientation) | `Overview.md` |
| A module / capability / requirement **spec** | `Modules/<Module>/<Capability>/…` |
| Releases, scope, the story map | `Roadmap/` |
| Why something was decided | `Decisions/` (active index: `Decision-Log.md`) |
| A past meeting / transcript | `Meetings/` |
| Risks, assumptions, open questions | `Risks-and-Assumptions.md` |
| Operational follow-ups / parking lot / bugs | `To-Do.md` |
| Customer requests / feedback | `Customer-Feedback/` |
| Competitor / market research | `Competitive-Intel/` |
| Persona, glossary, team | `Resources/` |
| A reusable workflow | `.claude/skills/` (see its `README.md`) |
| Where work & source live (Jira / Confluence / Figma / …) | `Resources/Tooling-Map.md` |
| Retired / historical material | `Archive/` (don't load unless the task is about history) |

Folder-specific conventions live in `.claude/rules/` and load automatically when you work in that folder.

## Before producing — clarify (don't assume)

Release? · Module/capability? · Output for (Jira / Confluence / brief / roadmap)? · Audience?

## Who can update this brain

This repo is shared, but only {{OWNER_NAME}} ({{OWNER_ROLE}}, the product owner of this brain)
should write to it.

- **Identity check:** before writing, editing, or capturing anything here, check whether the
  session's personal instructions identify the user as {{OWNER_NAME}}, {{OWNER_ROLE}}. That
  identity only loads from the owner's own private `~/.claude/CLAUDE.md` — it won't be present for
  anyone else, on any machine.
- **If confirmed the owner:** proceed normally — capture durable facts per the routing map, per the
  Rules below.
- **If not confirmed:** treat the session as read-only. Answer questions from the brain's content
  freely, but don't create, edit, or update any file in it — even if something notable comes up (a
  decision, a new requirement, feedback, a correction). Instead, say so in the response, e.g.:
  *"⚠️ This looks like it should be captured in the brain (e.g. `Decisions/Decision-Log.md`) — flag
  it to {{OWNER_NAME}} so they can log it."* Name the specific fact and where it would route.
- **Undocumented ≠ decided:** if the brain has no answer on a topic and you'd otherwise fill the
  gap with an inference, assumption, or best guess, don't present that as a settled decision or
  fact. Say plainly it isn't documented, that it may not reflect an actual decision, and that it
  needs confirmation from {{OWNER_NAME}} before anyone treats it as settled.
- **Offer to bridge back to the owner:** in that situation, offer to draft a short message or note
  (the question, the context/discussion, what's being assumed) that the person can send
  {{OWNER_NAME}} — so they can confirm, correct, or log it properly themselves.
- This is a courtesy control, not a security boundary — it depends on correctly reading loaded
  context, not on access control.

## Rules

- **Plan** multi-step work before acting; **verify** output against the spec/design before "done".
- **Check `Decisions/Decision-Log.md` first; never contradict a logged decision.**
- **Specs live here; Jira story cards are derived** — don't maintain two copies.
- **Capture** durable facts back into the brain, routed per the map above — only when the session
  is confirmed as the owner's (see "Who can update this brain").
- Favour the **simplest** solution that fully solves the problem.

## Active vs history

- **Active = lives in its folder.** Each folder's index (its README, or `Decision-Log.md` for decisions) lists only what's current.
- **Status** on every durable item: decisions (Accepted / Superseded), requirements (draft → … → done / descoped), releases (Scoping / In build / Shipped).
- **Retire by moving to `Archive/`**, mirroring the original path. Nothing is deleted.
- **Never load `Archive/`** unless the task is explicitly about history.
- **Git holds full history** (managed for you). Inline, keep only a one-line "why changed" plus a link to the replacement.

## Boundaries

- ✅ **Always:** follow logged decisions + each folder's `.claude/rules` conventions; use relative links; cite sources.
- ⚠️ **Ask first:** creating/editing Jira or Confluence; anything sent externally; non-trivial delete/overwrite.
- 🚫 **Never:** invent numbers or facts; contradict a decision; duplicate a spec into Jira and sync both by hand.

## Tools (Execution layer)

{{TOOLS_SUMMARY — one line naming the Jira projects (roadmap/portfolio project · delivery project(s) · ideas board), the Confluence space, and the key Figma files}}
Full pointers and what each tool is for: [`Resources/Tooling-Map.md`](Resources/Tooling-Map.md).
Use the connected MCP tools to ship work; always link the exact node/page.
