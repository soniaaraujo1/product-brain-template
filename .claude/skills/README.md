# Skills — Catalog & Backlog

The master list of project skills (reusable workflows). Skills live in `.claude/skills/<name>/SKILL.md`
and run as `/<name>` when Claude Code runs in this folder. **This file is the plan, not the build** —
we scaffold here and build each skill properly when we pick it up.

Status: ✅ Built · 🔨 Planned (agreed) · 💡 Idea (not committed)

## Composition model — atoms & orchestrators

The architecture we're following: **small single-purpose skills (atoms) + thin orchestrators that
delegate to them.**

- An **atom** does one job and is useful on its own (capture a meeting, log a bug, format a card).
- An **orchestrator** chains atoms for a bigger job. It routes and delegates — it does **not**
  re-implement what an atom does. Each behaviour lives in exactly one place (DRY).
- Skills are *instructions, not functions*: an orchestrator's `SKILL.md` tells Claude to invoke the
  sub-skills via the normal skill mechanism, so they compose **by reference**.
- Shared rules live in `CLAUDE.md`, so every skill inherits the conventions (naming decisions,
  persona, Jira projects) without repeating them. Tool pointers live in `Resources/Tooling-Map.md`,
  so skills stay product-agnostic.

## Setup

| Skill | Job | Status |
|---|---|---|
| `onboard-brain` | Fresh template copy → interviewed, filled-in, working brain for one product | ✅ |

## Atoms

### Capture — inputs into the brain
| Skill | Job | Writes to | Status |
|---|---|---|---|
| `capture-meeting` | Transcript/notes → note + routed decisions, actions, questions | Meetings/, Decisions/, To-Do, Risks | ✅ |
| `log-feedback` | Customer feedback → filed, themed, linked to a capability | Customer-Feedback/ | 🔨 |
| `log-bug` | Capture/triage a bug → structured record → route | To-Do (bugs) or Jira | 🔨 |

### Shape & spec — intent into buildable work
| Skill | Job | Writes to | Status |
|---|---|---|---|
| `shape-idea` | Rough idea → shaping doc + epic + requirement breakdown | Modules/, Roadmap/ | ✅ |
| `build-prd` | A capability → full spec (capability README + requirement specs) | Modules/ | 🔨 |
| `design-to-spec` | A Figma file → requirement spec + acceptance criteria | Modules/ | 🔨 |
| `story-card` | A requirement spec → Jira-ready story card(s) → create in Jira | Jira (+ spec link) | ✅ |
| `roadmap-card` | An idea / launch → portfolio epic or initiative card (value prop + Problem/Solution/Scope + classifiers) → create in Jira | Jira (portfolio) + Roadmap/ | ✅ |

### Communicate — brain into outputs
| Skill | Job | Status |
|---|---|---|
| `roadmap-update` | New inputs → updated roadmap (+ wiki page) | 🔨 |
| `debrief` | Status / team summary across the brain (weekly review) | 🔨 |
| `brand-deck` | Idea/brief/data → presentation built on your company's slide template (external .pptx output) | 💡 |

### Maintain — keep the brain healthy
| Skill | Job | Status |
|---|---|---|
| `competitor-analysis` | Competitor research → gap analysis + recommendation | ✅ |
| `review-todos` | Triage To-Do + open questions; surface what's stale/overdue | 🔨 |

## Orchestrators — compose atoms

| Skill | Composes | Job | Status |
|---|---|---|---|
| `sync-inbox` *(scheduled)* | capture-meeting, log-feedback, log-bug + routing | Gather emails + messages + transcripts → classify each → delegate to the right atom to keep folders current | 🔨 |

The **spec pipeline** is a chain of atoms run in sequence, not a separate skill (yet):
`shape-idea → build-prd → design-to-spec → story-card → Jira`. Add a thin `spec-pipeline`
orchestrator only if we end up running it end-to-end often.

## Design notes to resolve before building

- **`sync-inbox`:** needs connectors (email, chat, a transcript source) plus a scheduled task. For
  determinism, do the *fetching* with a script/connector and the *judgement*
  (classify/route/summarise) by delegating to the atoms; consider fanning per-item to subagents.
  Build last.
- **Jira-writing skills** (`story-card`, `log-bug`) share one set of Jira conventions (project keys,
  issue types, required fields) — keep them in `Resources/Tooling-Map.md`, not in the skills.
- **`shape-idea`** currently overlaps `build-prd` / `story-card`; refactor it to be the pipeline
  front-end only so the atoms compose cleanly.
