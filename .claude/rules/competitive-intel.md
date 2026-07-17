---
paths: ["Competitive-Intel/**"]
---

# Working in Competitive-Intel/

- Our knowledge about the market and competitors.
- Structure: **one folder per competitor** (`Title-Case`), holding short folder-relative files:
  - `<Competitor>/README.md` — the profile / teardown (main doc)
  - `<Competitor>/battlecard.md` — the GTM one-pager
  - `<Competitor>/roadmap-comparison.md` (or `<topic>-comparison.md`) — focused deep-dives
  - `<Competitor>/resources/` — that competitor's binaries (decks, screenshots, source PDFs/images)
- Shared, cross-competitor material (market reports, general screenshots) → `Competitive-Intel/resources/`.
- Market scans not tied to one competitor → `market-<topic>.md` or `YYYY-MM-<topic>.md` at the CI root.
- `Competitive-Intel/README.md` indexes all competitors; keep it current when adding one.
- Method: analyses follow the 4-layer, depth-scalable method in the `competitor-analysis` skill
  (market frame → profile + Four Corners → persona-weighted, roadmap-aware capability scorecard →
  synthesis + battlecard). Score the **time dimension** (live / committed / later / none), not just presence.
- Tag every claim with an **evidence tier** (verified fact + source / vendor claim / inference) and a date.
  Separate **real vs. hype** (shipped vs. announced). Source **multi-channel**, not just the vendor's site.
- Frame everything through the primary persona (`Resources/Personas.md`). Keep recommendations tied to our roadmap.
- `/competitor-analysis` produces and maintains these.
