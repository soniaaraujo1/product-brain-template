---
paths: ["Decisions/**"]
---

# Working in Decisions/

**What lives here:** product and design decisions (ADRs), one file each. The source of "why".

**Where to write:**
- New decision: `ADR-00X-short-title.md` (next free number; numbers are permanent). Use `_TEMPLATE.md`.
- `Decision-Log.md` is the **index**. Add a row to its Active table (ADR, decision, date, link).

**Create vs update:** ADRs are immutable. Never rewrite a past decision; supersede it with a new one.

**Active vs history:**
- To reverse or replace a decision: write a new ADR, set the old one's status to "Superseded by ADR-0YY" with a one-line why, move its file to `Archive/Decisions/`, and move its index row to the Superseded list.
- A decision counts as "decided" only once it has an ADR here. Until then it is an open question in `Risks-and-Assumptions.md`.

**ADR shape:** `# ADR-00X — Title`, then Status (Accepted or Superseded) · Date · Context · Decision · Consequences. Link the requirements or roadmap items it affects.
