# Competitive-analysis framework toolkit

Pick by the job to be done. Default to lightweight: use the fewest frameworks that answer the decision. Full teardowns use most; quick compares use one or two. Everything is filtered through the primary persona.

## The four jobs → frameworks

| Job | Framework | Use it to |
|---|---|---|
| Understand the field | Porter's Five Forces; positioning/perceptual map; analyst market-structure | See structure and who really leads |
| Understand + predict a rival | Porter's Four Corners | Anticipate their next move, not just today |
| Decide who's better | Weighted feature matrix + Kano + JTBD | Grade, persona-weight, and score capabilities |
| Find where to win | Blue Ocean strategy canvas + Four Actions | Escape the feature race; find white space |
| Arm the field + learn | Battlecard (Know/Say/Show) + Win/Loss | Enable sales; close the intel loop |

## Porter's Four Corners (predict, don't just describe)

The one framework that makes a profile predictive. Four questions:
- **Drivers** — what motivates them: financials, strategic objectives, founder ambitions, culture, history (e.g. founders with a point to prove, an acquirer's platform agenda).
- **Assumptions** — what they believe about the market and themselves (often where blind spots live).
- **Strategy** — their current actions: products, positioning, pricing, go-to-market.
- **Capabilities** — what they can realistically do: data, tech, talent, capital, distribution.
Then synthesize: **"Given all four, what will they most likely do next, and how would they react if we move?"** Write a short *predicted moves* list. Source: [Mindtools](https://www.mindtools.com/aweqtfy/porters-four-corners-model/).

## Weighted feature matrix (the core "who's better")

Rows = features (grouped by capability area); columns = each vendor. Cells are **graded, never binary** (use the 0-3 scale in `scorecard.md`). Then **weight each feature by persona importance** and roll up to a composite. Read: high-weight + we trail = table-stakes gap (roadmap survival item); high-weight + we lead = press it in messaging. Source: [pmprompt](https://pmprompt.com/blog/competitive-analysis-framework), [Compttr](https://compttr.com/en/blog/feature-comparison-matrix-guide).

## Kano model (classify what a feature is worth)

Tag each feature: **table-stakes** (basic; absence hurts, presence is expected), **performance** (more is better, scales with satisfaction), or **differentiator/delighter** (unexpected upside). Rules of thumb: never lose on table-stakes; compete on performance; win on differentiators. "What delights today becomes table-stakes tomorrow," so re-classify every 6-12 months. Source: [Product School](https://productschool.com/blog/product-fundamentals/kano-model).

## Jobs-to-be-Done (anchor the matrix)

Build the feature list from the **jobs the persona hires the product for** (pull them from `Resources/Personas.md`), not a random checklist. Prevents winning the feature count but losing the job. Score how well each vendor does the *job*, not just whether a feature exists.

## Blue Ocean strategy canvas + Four Actions (find where to win)

Plot the **factors the category competes on** (x-axis) against the level each vendor offers (y-axis); each vendor is a **value curve**. Converging curves = commoditized sameness. A winning move is a curve that **diverges** — high where others are low, and introducing new factors. Design it with **Four Actions: Eliminate / Reduce / Raise / Create.** This is how "the why" becomes a leapfrog (a Created factor neither side offers) rather than a catch-up. Source: [Blue Ocean](https://www.blueoceanstrategy.com/tools/strategy-canvas/).

## SWOT (synthesis, grounded)

Only after the scorecard. Strengths/Weaknesses = internal (our relative position from the matrix); Opportunities/Threats = external (market, their moves from Four Corners). Every entry must trace to evidence in the analysis, not opinion.

## Porter's Five Forces (market scans)

For a whole-market view: rivalry, new entrants, substitutes, buyer power, supplier (data-source) power. Useful when the question is "how attractive/defensible is this space," not "beat vendor X."

## Analyst methodology to borrow (not to worship)

- **Gartner Magic Quadrant:** two axes, **Ability to Execute** (product, market share, sales, support) vs. **Completeness of Vision** (strategy, roadmap). Good for a positioning map. [Methodology](https://www.gartner.com/en/research/methodologies/magic-quadrants-research).
- **Forrester Wave:** scores **Current offering** + **Strategy** + **Customer feedback** separately, with published weights. [How to read](https://www.starsight.biz/2025/02/27/how-to-surf-the-forrester-wave/).
- **The key borrow:** score **current vs. future separately**. In a fast-moving category, roadmap credibility matters as much as today's feature set. Our scorecard bakes this in via the maturity dimension (live / committed / later / none).

## Battlecard + Win/Loss (arm and learn)

- **Battlecard (Klue "Know / Say / Show"):** Know = who they are + where each wins; Say = objection handling, quick dismisses, landmines to plant; Show = proof (customer story, demo moment). Keep it one page, prescriptive. [Klue](https://klue.com/blog/battlecard-best-practices).
- **Win/Loss:** the best primary intel. Feed reasons-we-won / reasons-we-lost back into the scorecard weights and the roadmap. [Klue](https://klue.com/blog/win-loss-analysis-guide).
