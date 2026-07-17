---
paths: ["Modules/**"]
---

# Working in Modules/  (the requirements area)

Hierarchy: **Module → Capability → Requirement spec.** The spec is the source of truth; **Jira cards are derived from it**, never the reverse.

**Where to write:**
- Module overview: `<Module>/README.md` (what it is + capability index).
- Capability overview: `<Module>/<Capability>/README.md` (active requirements table + any behaviour shared across its requirements).
- A requirement: `<Module>/<Capability>/<requirement>.md`, named for the requirement in kebab-case, never after a Jira key.

**Create vs update:**
- New behaviour: new requirement spec (copy `_templates/requirement.md`); add a row to the capability table.
- Changed behaviour: edit the spec in place. Git keeps the prior version.

**Active vs history:**
- `Status` field on every spec: draft, groomed, ready, in build, done, or descoped.
- Descoped or removed: move the file to `Archive/Modules/<same path>`, drop its row from the capability table, leave a one-line why.

**Jira:** derived card keys live only in the spec's "Derived Jira cards" section. Cards can churn; the spec stays put.

Create items from `_templates/` or run `/shape-idea`.
