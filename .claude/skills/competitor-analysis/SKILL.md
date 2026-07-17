---
name: competitor-analysis
description: Research a competitor or market topic and produce a rigorous, framework-driven competitive analysis (profile, predicted moves, a persona-weighted + roadmap-aware capability scorecard, gaps, a strategic recommendation, and a sales battlecard) filed in Competitive-Intel/. Use when the user says "analyze competitor X", "how do we compare to Y", "competitive teardown", "feature comparison / scorecard", "battlecard", or "what's the gap vs the market".
---

# Competitor Analysis

Produce a grounded, decision-useful competitive analysis using a defined method, not free-form notes. The method is layered and **depth-scalable**: match effort to the ask.

Act like a competitive-intelligence analyst: separate fact from claim, score against the persona, and always add the time dimension (what is live vs. committed vs. later). A static "who has what" is misleading in a fast-moving category.

## Pick the depth mode first

| Mode | When | Do layers | Output |
|---|---|---|---|
| **Quick compare** | "How do we compare on X?" one capability / fast answer | 0, mini-3, 4-rec | Short note, or added to the competitor's `README.md` |
| **Battlecard** | GTM/sales needs ammo now | 0, 2 (essentials + real-vs-hype), 4-battlecard | `<Competitor>/battlecard.md` |
| **Full teardown** | Strategic threat / renewal / board ask | all, multi-channel | `<Competitor>/README.md` (+ companions in the folder) |
| **Market scan** | Understand the field / several players | 1 (heavy), light 2 per player, positioning map | `market-<topic>.md` at the CI root |

Layer 0 = scope: confirm the competitor/topic, the **decision it serves**, and the **persona lens** before starting. Ask only what you can't infer.

## The method (4 layers)

**Layer 1 — Market frame** *(light; full in a market scan)*
Where the field sits and **who actually leads** (cite analyst market-structure for your category, e.g. Gartner / Forrester buckets, not the vendor's self-claim). Optional: Porter's Five Forces, a 2-axis positioning map. → `references/frameworks.md`.

**Layer 2 — Competitor profile + Four Corners**
Company facts (funding, scale, health, pricing, trajectory) **plus Porter's Four Corners** (drivers, assumptions, strategy, capabilities) to *predict their next moves*, not just describe today.
- Source **multi-channel**, not just their website. → `references/sourcing-and-evidence.md`.
- Tag every claim with an **evidence tier** (verified fact / vendor claim / inference) and a date.
- Separate **real vs. hype**: shipped-and-evidenced vs. announced-only.

**Layer 3 — Capability scorecard** *(the core "who's better")*
A persona-weighted, Kano-classed, JTBD-anchored, **roadmap-aware** feature matrix with a composite score. Score **maturity (live / committed / later / none) for both sides**, not just presence. → `references/scorecard.md`.

**Layer 4 — Synthesis + outputs**
- **Strategy-canvas / Four Actions** read → where curves converge (sameness) and where we can diverge (white space / leapfrog).
- **SWOT** grounded in the scorecard (not vibes).
- **Gap analysis** (persona-weighted) + a **differentiation thesis**.
- **Recommendations**: 2-4 prioritized moves, each tied to a roadmap item or a decision.
- **Battlecard** (Know / Say / Show) when there's a GTM audience. → `references/templates.md`.

## Procedure

1. **Scope & mode** (Layer 0).
2. **Know our side first.** Read `Overview.md`, the relevant `Modules/`, and **`Roadmap/`** (README, Vision, the relevant initiative). The roadmap read is mandatory: our answer to a gap is often already on it, at a horizon that matters.
3. **Research multi-channel** (Layer 2 sourcing).
4. **Profile + Four Corners** (Layer 2).
5. **Build the scorecard** (Layer 3).
6. **Synthesize** (Layer 4): canvas, SWOT, gaps, differentiation.
7. **Recommend + battlecard.**
8. **File it** in the competitor's folder using the templates (`<Competitor>/README.md` + companions + `resources/`); update `Competitive-Intel/README.md`; cross-link modules/roadmap/decisions/feedback; graduate work via `/shape-idea` and decisions via `Decisions/`.

## Guardrails

- **Evidence discipline.** Fact (source + date) ≠ vendor claim ≠ inference. Label which. Never invent numbers; when a vendor's own numbers are inconsistent across sources, say so (it's a finding).
- **Persona lens.** A feature only matters if it serves the primary persona (see `Resources/Personas.md`). Weight accordingly.
- **Roadmap-aware.** Always score the time dimension for both sides. Distinguish our *committed* scope from *direction* (`Roadmap/Vision.md` is direction, not commitment) and flag undocumented framing as not-yet-decided.
- **Real vs. hype.** Shipped ≠ announced. Demand product-level evidence for "it's live" claims.
- **Actionable + tied to our roadmap**, never generic.
- **Write access:** only the brain's owner updates the brain (see root `CLAUDE.md`); otherwise deliver read-only and flag what to capture.

## References

- `references/frameworks.md` — the toolkit (Four Corners, feature matrix, Kano, JTBD, strategy canvas, SWOT, Five Forces, analyst methodology, battlecard/win-loss): what each answers, when to use, how to apply here.
- `references/scorecard.md` — the weighted, roadmap-aware capability-matrix rubric + template + how to read it.
- `references/sourcing-and-evidence.md` — the multi-channel source checklist, evidence tiers, real-vs-hype test, recency.
- `references/templates.md` — output skeletons: the competitor profile, battlecard, companions (roadmap comparison, market scan).
