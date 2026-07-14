# Project conventions

## Cross-agent skill compatibility

- Treat this repository as a cross-agent skill collection.
- Keep each skill's portable definition in `SKILL.md`.
- Do not create or commit `agents/openai.yaml`; it is OpenAI-specific metadata that the other supported agents do not use.
- If a skill scaffolding tool generates `agents/openai.yaml`, remove it before committing.
