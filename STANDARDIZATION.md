# Standardization (Template Lab)

OpenForge standardization is based on the `coff33ninja/template_lab` repository. It provides language-specific templates, a manifest that describes each template, and a PowerShell scaffold script. Use it to keep new projects consistent across languages.

## What Template Lab Provides
- Templates are declared in `templates/manifest.json`.
- New projects are scaffolded with `scripts/new-project.ps1`.
- The template catalog covers PowerShell, CMD, Python, Node, Go, Flutter, Kotlin, React, static web, Rust, and multiple library templates.
- Workspace stacks exist for multi-project setups like `db-react-worker`, `go-api-flutter-contracts`, and `library-pack`.

## Template Contract (What We Expect In Projects)
Template entries define install/check strategies, required tools, required files, and default entrypoint and test file expectations. OpenForge projects should preserve these baseline files and behaviors unless there is a strong reason to deviate.

## Recommended Workflow
1. Clone `coff33ninja/template_lab`.
2. Run `pwsh -File .\scripts\new-project.ps1 -Template <name> -Name <project> -Destination <path>`.
3. Move or create the project under `OpenForge-Projects/`.
4. Add AI transparency files (`AI_CONTRIBUTION.md`, `.ai_logs/`).
5. Update `OpenForge-Manifest/catalog.json`.

## If You Do Not Use Template Lab
Use `OpenForge-Projects/project_template/` and align with `DEBUT_CHECKLIST.md`.
