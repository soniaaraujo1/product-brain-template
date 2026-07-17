# Portfolio project fields — discover once, record here, reuse

Every org's portfolio Jira project has its own custom fields and dropdown values, so this file
ships empty of specifics. **On first write, discover the real fields, fill the map below, and
commit it** — every later run reads this file instead of re-discovering.

## One-time discovery (first write to the portfolio project)

1. **Identify the portfolio project** from `Resources/Tooling-Map.md` (key + site). If none is
   listed, ask the user where roadmap epics live.
2. **Fetch the field metadata live:** `getJiraProjectIssueTypesMetadata` for the issue types, then
   `getJiraIssueTypeMetaWithFields` per type (Epic / Initiative) for the fields, which are
   required, and each dropdown's `allowedValues`.
3. **Fill in the two sections below** (field map + dropdown values), stamp the date, and commit —
   per the "capture durable facts" rule in `CLAUDE.md`.

If writes later start failing on a field, re-run discovery; admins change these.

## Field map *(recorded: YYYY-MM-DD — unfilled means discovery hasn't run yet)*

The first rows are standard Jira and true everywhere; add your project's custom fields below them.

| Card element | Field name | Key | Type | How to set |
|---|---|---|---|---|
| Title | Summary | `summary` | text | top-level `summary` param (required) |
| Description | Description | `description` | rich text | top-level `description` param as markdown, with `contentFormat: "markdown"` |
| Priority | Priority | `priority` | select | `{"name": "High"}` |
| Release | Fix versions | `fixVersions` | version list | `[{"name": "<release>"}]` |
| Parent (epic only) | Parent | `parent` | issue link | top-level `parent` param |
| *Value proposition (if a custom field)* | | `customfield_xxxxx` | rich text | ADF doc in `additional_fields` (see below) |
| *Owning team / squad (if used)* | | `customfield_xxxxx` | single select | `{"value": "<exact>"}` |
| *Other classifiers (if used)* | | | | |

## Dropdown values *(copy verbatim from `allowedValues` — they are validated on write)*

- **<Classifier>:** `<value>` · `<value>` · …

Watch for near-duplicate strings across fields (e.g. "and" vs "&", "ELT" vs "ETL" style
inconsistencies are common). Always copy the exact string for the field you are setting. Which
team is "ours" comes from `Resources/Tooling-Map.md` / `Resources/Team.md`.

## Mechanics that hold on any Jira Cloud site

**Releases (Fix versions) change often, so fetch them live.** Do not trust a hardcoded list. Read
the current `allowedValues` right before writing, or check a couple of recent cards. If the target
release is not yet a value in Jira, leave it out and flag it rather than inventing a version name.

**Finding the parent initiative (for an epic).** Find candidates with JQL:

```
project = <PORTFOLIO_KEY> AND issuetype = Initiative ORDER BY updated DESC
```

Confirm the right parent with the user before linking. Never guess the parent.

**The write.** Primary call is `createJiraIssue`:

- `cloudId`, `projectKey`, `issueTypeName: "Epic"` or `"Initiative"`
- `summary` (the title)
- `description` (markdown string) with `contentFormat: "markdown"`
- `parent` (the initiative key) when creating an epic under an initiative
- `assignee_account_id` (default to this brain's owner unless told otherwise; look up with
  `lookupJiraAccountId` on the owner's email in `Resources/Team.md`)
- `additional_fields` for everything else

**The description takes markdown; use bold section labels.** No markdown `#` headings: the house
style renders section names as bold lines closed by horizontal rules:

```
**Problem**

<one tight paragraph>

---

**Solution**

<one tight paragraph, bullets allowed for the moving parts>

---

**Scope of work**

* <what is in>
* <what is in>

---
```

**Rich-text custom fields need ADF, not markdown.** Connectors typically convert markdown only for
the `description`; a plain string into a rich-text custom field (e.g. a Value Proposition field)
will be rejected or mangled. Send an ADF document object:

```json
{
  "type": "doc", "version": 1,
  "content": [
    {"type": "paragraph", "content": [
      {"type": "text", "text": "For the business: ", "marks": [{"type": "strong"}]},
      {"type": "text", "text": "<business value in one or two sentences>"}
    ]},
    {"type": "paragraph", "content": [
      {"type": "text", "text": "For users: ", "marks": [{"type": "strong"}]},
      {"type": "text", "text": "<user value in one or two sentences>"}
    ]}
  ]
}
```

One side only: include just the paragraph that applies. If a write fails specifically on a
rich-text custom field, create the card without it, then set it with `editJiraIssue` passing the
same ADF object in `fields`.

## After creating

1. Return the new issue URL (the `webUrl`).
2. Capture it back into the brain: add or update the entry in `Roadmap/` (`README.md` for the
   portfolio view, or the relevant `<Initiative>.md` / `Release-N.md`) with the new key and a
   one-line description.

## No portfolio project?

If roadmap epics live in the delivery project, write there with the same card format (skip the
missing classifiers). If the roadmap doesn't live in Jira at all, deliver the card as text for
wherever it lives and file it under `Roadmap/` so the brain stays the source of truth.
