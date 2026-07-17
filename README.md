# Product Brain — a template

A git-native, AI-readable "second brain" for a product team, designed to be operated with
[Claude Code](https://claude.com/claude-code) (or any agent that reads `CLAUDE.md`). Copy it, run
`/onboard-brain`, and it becomes the durable memory of **your** product: decisions, requirements,
roadmap, meetings, customer feedback, and competitive intel in one linked, queryable place.

The goal, borrowed from the *New Ways of Working* model: **stop starting every task from zero.**

> The problem is not how fast the team works. It's how much context gets lost along the way.

Most product work is operational (tickets, docs, status updates), and the context behind *why*
lives in people's heads, scattered chat threads, and meeting transcripts nobody re-reads. This
brain is the durable, queryable record. A new joiner should get **full context in one read —
hours, not months.**

## Adopt it in three steps

1. **Copy this repo** ("Use this template" on GitHub, or clone and re-point the remote). One brain
   per product.
2. **Open it in Claude Code and run `/onboard-brain`.** It interviews you about the product, the
   team, the personas, and your tool stack, then fills in every `{{placeholder}}` — including this
   README.
3. **Push, and have the team clone it.** Pull before you start, push what you capture; every
   person and every agent session works from the same context.

## The four layers

1. **Capture** — every meeting and conversation becomes context (drop transcripts into `Meetings/`).
2. **Network Thinking** — it all lives here, linked, as one source of truth.
3. **Orchestration** — `CLAUDE.md` + the skills in `.claude/skills/` define *how* the assistant acts.
4. **Execution** — work ships into the tools you already use (Jira, Confluence, Figma, … via MCP).

## What's inside

```
CLAUDE.md                 The agent guide: routing map, rules, boundaries, write control
Overview.md               The product in one read (start here)
Modules/                  Requirements area: Module → Capability → Requirement spec
Roadmap/                  Horizons, initiatives, releases, vision (+ _templates/)
Decisions/                ADRs, one file each; Decision-Log.md is the active index
Meetings/                 Dated meeting notes; items get routed, not just summarised
Customer-Feedback/        Voice of the customer; informs the roadmap, isn't the roadmap
Competitive-Intel/        Competitor teardowns, battlecards, market scans
Resources/                Personas, glossary, team, tooling map (where work ships)
Risks-and-Assumptions.md  Live register of risks, assumptions, open questions
To-Do.md                  Follow-ups, parking lot, pre-Jira bug capture
Archive/                  Retired content, moved (never deleted), mirroring its path
.claude/rules/            Per-folder conventions, loaded automatically in that folder
.claude/skills/           The reusable workflows (see the catalog in its README.md)
```

## The skills

| Skill | What it does |
|---|---|
| `/onboard-brain` | First run: interview → filled-in, working brain for your product |
| `/capture-meeting` | Transcript → filed note + routed decisions, actions, questions |
| `/shape-idea` | Rough idea → shaping doc + epic + requirement breakdown |
| `/story-card` | A functionality → consistent, gap-checked story card (→ Jira) |
| `/roadmap-card` | A launch/bet → portfolio epic or initiative card (→ Jira) |
| `/competitor-analysis` | A rival or market → framework-driven teardown, scorecard, battlecard |

## Design principles

- **Routing over loading.** `CLAUDE.md` maps every task type to one folder; the agent reads what
  the task needs, nothing more.
- **Specs lead, tickets follow.** Requirement specs are the source of truth; Jira cards are derived
  from them, never maintained as a second copy.
- **Decisions are immutable.** ADRs get superseded, never rewritten. Undocumented ≠ decided.
- **Active vs history.** Each folder's index lists only what's current; retired material moves to
  `Archive/`, mirroring its path. Git holds full history, so files stay clean.
- **One writer.** The brain has a named owner; everyone else (and their agent sessions) reads and
  flags. See "Who can update this brain" in `CLAUDE.md`.
- **Markdown only, one idea per file, linked liberally** with relative links.

## How it grows (the scale model)

This is the **Team Brain** — the one you build first. The same pattern scales outward later:

- **Organisation** — standards, compliance, architecture, company principles (all teams)
- **Division** — strategy, roadmaps, cross-team dependencies, OKRs (Heads of Product)
- **Team** — decisions, requirements, ADRs, sprint history ← *you are here*
- **Personal** — your own notes, workflows, prompts

## License

[MIT](LICENSE). Use it for any product, any company.
