---
name: capture-meeting
description: Turn a meeting transcript or raw notes into a clean, filed meeting note for this product brain — extracting decisions, action items, and open questions and routing each to the right place. Use when the user shares a transcript, says "capture this meeting", "process these notes", or pastes notes from a grooming, walkthrough, sync, or stakeholder call.
---

# Capture Meeting

Turn a transcript or raw notes into durable, linked context in this brain.

## Inputs
- A transcript, notes, or a path/paste from the user. If none is provided, ask for it.
- If the meeting date or attendees are unclear, ask (don't invent them).

## Steps
1. **Read** the source and identify: topic, date, attendees, purpose.
2. **Draft the note** in `Meetings/YYYY-MM-DD-short-topic.md` using the structure in
   `Meetings/_TEMPLATE.md` (Summary, Decisions, Action items, Open questions, Notes).
3. **Extract and route** — don't just summarise, *file* each item:
   - **Decisions** → also append an `ADR-0XX` entry to `Decisions/Decision-Log.md` (append-only;
     next number in sequence). Link the note ↔ the ADR.
   - **Action items** → list with owner + due in the note; if any creates buildable work, offer to
     run `/shape-idea`.
   - **Open questions / risks** → also add to `Risks-and-Assumptions.md`.
   - **New requirement** mentioned → note it and offer to draft a story card into the right
     capability under `Modules/`.
4. **Link** every referenced artifact (Figma node, Confluence page, module/capability, decision)
   with a relative link into the brain.
5. **Apply conventions** in `CLAUDE.md` and respect existing decisions in `Decisions/`.
6. **Report back** a short list of what you filed and where, and flag anything you were unsure about
   rather than guessing.

## Guardrails
- Never fabricate attendees, dates, or decisions. Mark anything reconstructed/uncertain as `(confirm)`.
- Keep the note tight; put verbatim detail under "Notes" only if it's worth keeping.
