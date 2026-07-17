# The capability scorecard (roadmap-aware feature matrix)

The heart of "who's better." A weighted, persona-anchored, time-phased matrix that rolls up to a composite. Rigorous but lightweight: aim for ~15-30 features across 5-8 capability areas for a full teardown, fewer for a quick compare.

## Build it in five moves

1. **Decompose by job, then feature.** Group features under capability areas anchored on persona jobs-to-be-done (from `Resources/Personas.md`). Not a scraped feature list.
2. **Weight each feature** by importance to the primary persona: **3 = must-have, 2 = important, 1 = nice-to-have.**
3. **Kano-class each feature**: table-stakes / performance / differentiator.
4. **Score each vendor** on the 0-3 scale below, and record **maturity** (the time dimension) for each side.
5. **Roll up**: weighted score per area and overall (see below). Then read it (rules at the bottom).

## Scoring scale (per vendor, per feature)

| Score | Meaning |
|---|---|
| **0** | Absent. Not offered and not planned. |
| **1** | Partial or roadmap-only. Weak, or announced/committed but not live. |
| **2** | Live parity. Shipped, works, comparable to the field. |
| **3** | Differentiated / best-in-class. Shipped and clearly ahead. |

Pair every score with an **evidence tier** (A verified / B vendor claim / C inference — see `sourcing-and-evidence.md`). A "3" needs tier-A evidence.

## Maturity dimension (score the clock, not just the state)

Record for each side, because roadmap credibility matters as much as today's features:

| Maturity | Meaning |
|---|---|
| **Live** | In production now (with evidence). |
| **Committed** | On the roadmap with a date/epic. |
| **Later** | Direction only; not scoped or dated (e.g. our `Roadmap/Vision.md` items). |
| **None** | Not on the roadmap at all (a true white space). |

A rival at **Live** vs. us at **Later** on a weight-3 feature is a red flag even if our vision is better. Say so explicitly.

## Template (copy this)

| Capability area | Feature (JTBD) | Weight (1-3) | Kano | Us: score · maturity | Them: score · maturity | Evidence (tier · source) | Edge |
|---|---|---|---|---|---|---|---|
| <core job area> | <a job the persona must get done> | 3 | table-stakes | 1 · Later | 2 · Live | A · product docs | Them |
| AI | Conversational NL assistant | 3 | performance | 1 · Later | 2 · Live (date) | A · demo video | Them |
| AI | <a factor neither side offers yet> | 3 | differentiator | 1 · Later | 0 · None | A · both vendors' docs | Open field |
| Data | <a data capability we've committed> | 3 | performance | 2 · Committed | 1 · unclear | B · roadmap | Us |

## Roll-up

- **Weighted feature score** = weight x vendor score.
- **Area score** = sum(weighted) / max-possible for that area, as a %.
- **Composite** = same across all areas. Report per-area and overall for each vendor.
- Keep the math visible and simple; the point is relative signal, not false precision.

## How to read the completed matrix

- **High weight + we trail (score gap ≥ 1)** → table-stakes/survival gap. Candidate for the top of the roadmap. If it's also "Them: Live / Us: Later," it's urgent.
- **High weight + we lead** → press it in positioning and the battlecard.
- **Differentiator + both low/None** → white-space leapfrog. Run it through Four Actions (Create) in `frameworks.md`.
- **Low weight, either way** → ignore; don't let it drive roadmap or messaging.
- **Cluster of parity across a high-weight area** → commoditized; compete on data quality, UX, price, or a Created factor, not features.

## Keep it honest

- Don't inflate our scores or deflate theirs; the scorecard is only useful if it survives a skeptic.
- Where evidence is tier-B/C, mark the score provisional.
- Re-weight from win/loss reality when available; re-run Kano every 6-12 months (yesterday's differentiator is tomorrow's table-stake).
