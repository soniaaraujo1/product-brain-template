# Output templates

Every artifact follows one of these skeletons so the brain stays consistent. Keep sections tight and high-signal; drop sections that don't apply in lighter modes. No em dashes (house style). Cross-link modules, roadmap, decisions, and feedback.

## `<Competitor>/README.md` — full profile / teardown

```
# <Name>

**Status** · **Last updated** · **Owner**
**Category** · one line on who they are and where they compete.

> Read-this-first framing box: the single most important strategic point (the "so what"),
> kept in proportion (respect the threat, but don't inflate it).

## 1. Company & trajectory
Table: founded, funding, revenue (est.), headcount, customers, pricing, recognition, trouble signals.
Each row tagged with confidence/source.

## 2. Product suite
What they actually sell today, product line by product line.

## 3. [Their key battleground] — real vs. hype
For a fast-moving axis (e.g. AI): a table of moves, dates, and a real/hype verdict each.

## 4. [Named customer/renewal claims] — verified
If specific claims are in play (e.g. from a renewal), verify each with a verdict + evidence.

## 5. Data foundation & methodology
Their data claims (flag inconsistent numbers) + independent quality signals.

## 6. Voice of the market
Reviews, employee sentiment, analysts, community — what people actually say. Separate from marketing.

## 7. Positioning & how they sell
Category language, personas, channel, attack lines, analyst air cover.

## 8. Four Corners → predicted moves
Drivers · Assumptions · Strategy · Capabilities → a short "what they'll likely do next" list.

## 9. Capability scorecard  (link to companion if large)
The weighted, roadmap-aware matrix (see scorecard.md). Current-state table + note the time view.

## 10. Gaps that matter (persona-weighted)
Where they lead and it hurts; where we can press (their soft spots).

## 11. Recommendation
2-4 prioritized moves, each tied to a roadmap item or a decision. Offer /shape-idea, flag decisions.

## Sources & channels covered
Grouped by channel. Explicitly note blocked/thin channels and caveats.
```

## `<Competitor>/battlecard.md` — GTM one-pager (Know / Say / Show)

```
# Battlecard: <Name>   ·   updated <date>   ·   owner

## Know (30-second brief)
Who they are, category, where they genuinely win, where they're weak. Their pricing.

## Where WE win  (lead with these)
3-5 proof-backed advantages, phrased as customer value.

## Where THEY win  (don't hide it)
Honest list + the reframe for each.

## Objection handling
"They say X" → our response. Include the real-vs-hype punctures.

## Landmines to plant
Questions that expose their weak spots (data depth outside core geos, hype vs shipped, hidden cost, onboarding lift).

## Quick dismisses
One-liners for when they come up unprompted.

## Proof (Show)
Customer story, demo moment, or metric that lands the point.

## Win/Loss notes
Recent reasons we won/lost vs. them; win-rate if known. Update from the field.
```

## Companions (use when a teardown gets large)

- **`<Competitor>/roadmap-comparison.md`** (or `<topic>-comparison.md`) — a focused deep-dive that would bloat the profile (e.g. a **roadmap-aware / time-phased** comparison, or a single-capability scorecard). Cross-link from the profile's scorecard section.
- **`market-<topic>.md`** (or `YYYY-MM-<topic>.md`, at the CI root) — a **market scan**: Five Forces / positioning map across several players; who leads; where we fit. Lighter per-player profiles link out to full teardowns.

## Filing rules

- **One folder per competitor** (`Title-Case`), holding short folder-relative files: `<Competitor>/README.md` (profile), `<Competitor>/battlecard.md`, `<Competitor>/roadmap-comparison.md`.
- **Binaries** (decks, screenshots, source PDFs/images) go in `<Competitor>/resources/`; **shared cross-competitor** material in `Competitive-Intel/resources/`.
- Keep `Competitive-Intel/README.md` (the competitor index) current when adding a competitor.
- Follow `.claude/rules/competitive-intel.md`. Graduate work items via `/shape-idea`; log real decisions in `Decisions/`.
