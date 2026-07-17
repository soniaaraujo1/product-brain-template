---
paths: ["Archive/**"]
---

# Working in Archive/

The single home for retired content: shipped or abandoned releases, closed risks, superseded decisions, descoped requirements.

- **Do not load this folder** unless the task is explicitly about history (for example "why did we change X", "what did the last release use to include").
- Retire by **moving** the file here, mirroring its original path: `Archive/Decisions/…`, `Archive/Modules/…`, `Archive/Roadmap/…`. Nothing is deleted, so links survive.
- On the moved file, set its status to the retired state and add a one-line pointer to whatever replaced it.
- Full history is in git. This folder is just the human-browsable record.
