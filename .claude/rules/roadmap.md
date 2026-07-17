---
paths: ["Roadmap/**"]
---

# Working in Roadmap/

If a story map exists (see `Resources/Tooling-Map.md`), it is the source of truth for **shape**;
this folder owns **scope decisions and their rationale**.

**Where to write:**
- Portfolio index + horizons (Now / Next / Later) across all initiatives: `README.md`.
- A specific initiative's scope (its now + later): `<Initiative>.md` (from `_templates/initiative.md`).
- A specific release: `Release-N.md` (scope in/out, links to specs and decisions; from `_templates/release.md`).
- Story-map structure and gaps: `Story-Map.md`.
- Long-term bets, net-new capabilities, parking-lot descriptions: `Vision.md`.

**Create vs update:** edit the release file in place when scope changes. Record each in/out move in a "Scope changes" list with date and why.

**Active vs history:**
- `Status` on each release: Scoping, In build, or Shipped.
- A shipped or abandoned release moves to `Archive/Roadmap/` once it is no longer the active reference.

Link items to their spec in `Modules/…` and the decisions in `Decisions/…`.
