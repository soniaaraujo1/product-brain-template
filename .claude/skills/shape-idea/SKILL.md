---
name: shape-idea
description: Turn a raw product idea into a shaping doc plus an epic and a feature/story breakdown ready for Jira, grounded in this product brain. Use when the user has a new idea, feature, or capability and says "shape this", "break this into stories", "turn this into an epic", or "what stories do we need for X".
---

# Shape Idea

Take a rough idea and turn it into structured, buildable work that fits the product.

## Steps
1. **Ground it in the brain first.** Before shaping, read the relevant context:
   - `Overview.md`, and the relevant module/capability under `Modules/` (which module/capability
     does this touch? is it a new capability or a new requirement on an existing one?)
   - `Decisions/Decision-Log.md` (don't contradict a decision)
   - The active release and story-map files under `Roadmap/` (is this current-release or later?
     does a story already exist?)
   - `Resources/Personas.md` (frame the story for the primary persona)
2. **Clarify before producing** (per `CLAUDE.md`): which release, which module/capability, what's
   the output for, who's the audience. Ask if unclear.
3. **Write a shaping doc** — problem, who it's for, the proposed approach, what's in/out, open
   questions, and how it maps onto the roadmap. Save under `Roadmap/` or offer to put it in Confluence.
4. **Break it down** — propose an **Epic** and the **features/requirements** beneath it. For each,
   write a title in our `[Location] Functionality` format and a one-line persona user story.
5. **Format each requirement** using the `requirement` template (`Modules/_templates/requirement.md`)
   and the `story-card` skill, so output matches our standard. Save each into its capability folder:
   `Modules/<Module>/<Capability>/<requirement-name>.md` (record the Jira key inside the file once
   it exists).
6. **Offer to ship** — once approved, create the epic/stories in **Jira** (the delivery project in
   `Resources/Tooling-Map.md`) via the Atlassian MCP, and link each brain file to its Jira key.

## Guardrails
- Surface conflicts with existing decisions or scope instead of silently overriding them.
- Mark genuinely-undecided points as open questions (→ `Risks-and-Assumptions.md`), with an interim
  assumption — don't invent answers.
- Don't create Jira issues without explicit confirmation.
