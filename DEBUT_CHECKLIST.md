# OpenForge Debut Checklist

Use this checklist before you list a project in `OpenForge-Manifest/catalog.json`.

## Minimum (Must Have)
- [ ] Project has a clear name and unique ID (reverse-domain style)
- [ ] `README.md` with summary, features, install, usage, and status
- [ ] `AI_CONTRIBUTION.md` with honest AI vs human breakdown
- [ ] Prompt vault exists (`.ai_logs/` or `prompts/`)
- [ ] `.gitignore` and `.gitattributes` present
- [ ] Clear entrypoint exists and is documented
- [ ] Tests folder or placeholder exists
- [ ] Release artifact or explicit status (`alpha`, `beta`, `paused`)
- [ ] License declared
- [ ] Manifest entry added with icon and at least one screenshot
- [ ] Tech stack declared (language + runtime)

## Recommended (Should Have)
- [ ] `docs/architecture.md` explaining system design
- [ ] `docs/security.md` with permissions and threat notes
- [ ] `docs/troubleshooting.md` for common issues
- [ ] `CHANGELOG.md` or `docs/changes.md`
- [ ] Basic tests or a note explaining why tests are missing

## If Hardware Is Required
- [ ] `docs/hardware.md` with parts list and wiring
- [ ] `hardware/` assets (diagrams, ESPHome, STL) if applicable
- [ ] Manifest flag `requires_hardware: true` and `hardware_notes`

## If Using a Desktop Agent
- [ ] `docs/agent.md` with protocol and setup
- [ ] Manifest flag `agent_supported: true`

## If It Is a Bot or AI Service
- [ ] `system_instructions/` or `docs/bot.md` with core logic
- [ ] `datasets/` or clear data reproduction steps
- [ ] AppStore action is `Clone Architecture` instead of `Install`

## If It Is a Script or CLI Tool
- [ ] Clear entrypoint (`.ps1`, `.cmd`, `.py`, `.js`) documented
- [ ] Runtime requirements listed (PowerShell version, Python version, Node version)
- [ ] Example commands included in README

## AppStore Quality
- [ ] Icon in `OpenForge-Manifest/icons/`
- [ ] 1-3 screenshots in `OpenForge-Manifest/screenshots/`
- [ ] Tagline and description are clear and non-hyped

## Transparency Bar
- [ ] Hallucination fixes documented in `.ai_logs/hallucination_fixes.md`
- [ ] Major AI prompts recorded in `.ai_logs/architecture_prompts.md`
