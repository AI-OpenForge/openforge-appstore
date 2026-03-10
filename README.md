# OpenForge (Ecosystem Overview)

OpenForge is a transparent, AI-assisted software lab. The ecosystem is intentionally split into three pillars to keep the catalog, client, and project code cleanly decoupled.

**Pillars**
1. `OpenForge-AppStore/`: The showcase client (Android app) that renders the catalog.
2. `OpenForge-Manifest/`: The static manifest that powers the client.
3. `OpenForge-Projects/`: The project lab containing source code and AI transparency logs.

**Why This Structure**
- Prevents the AppStore from breaking when projects are unstable.
- Keeps the manifest as the single source of truth.
- Enforces consistent design via a shared UI kit.

**How Updates Flow**
1. Build or update a project in `OpenForge-Projects/`.
2. Publish release artifacts (APKs/binaries) in the project.
3. Update `OpenForge-Manifest/catalog.json` with new metadata.
4. The AppStore reflects changes on next refresh.

**AI Transparency**
Every project should include:
- `AI_CONTRIBUTION.md`
- `.ai_logs/` or `prompts/` with key prompts and corrections

**Optional Ecosystem Extensions**
- `OpenForge-Agent/` as a shared desktop agent.
- `OpenForge-DesignSystem/` if the UI kit needs to be shared across repos.

**Standardization**
- Use `coff33ninja/template_lab` for scaffolding when possible.
- See `STANDARDIZATION.md` for workflow and template alignment.

**Quick Start**
- Start with three projects: `lumos`, `openremote`, `coffeedl`.
- Keep UI consistent by using the AppStore `ui_kit` components.
- Use `catalog.json` as the authoritative index.

---

# OpenForge-AppStore

Showcase client for the OpenForge ecosystem. This app is a clean, consistent gallery that reads the manifest and presents projects to the public. It does not contain project source code or build artifacts.

**Purpose**
- Present all OpenForge projects in a consistent UI.
- Fetch data from `OpenForge-Manifest/catalog.json`.
- Provide clear actions per project, such as `Install`, `View Source`, or `View Hardware`.

**What This Is Not**
- Not a backend.
- Not a project repository.
- Not a storage location for APKs or binaries.

**Data Flow**
1. App loads and fetches the manifest JSON.
2. UI renders projects based on `category`, `platforms`, and `actions`.
3. Tapping a project opens detail view and actions.

**Folder Layout**
- `lib/`: App code.
- `lib/screens/`: Home, detail, filters, dev logs, and about.
- `lib/ui_kit/`: Shared UI components and theme tokens that prevent AI UI drift.
- `lib/services/`: Manifest fetcher, caching, and version checks.
- `assets/`: Branding, logos, and static images.

**UI Consistency Rules**
- All screens must use components from `lib/ui_kit/`.
- Avoid custom ad-hoc widgets unless the UI kit is updated.
- Typography and colors are defined once and reused everywhere.

**Recommended Screens**
- Home: Featured and recent projects.
- Categories: Mobile, Desktop, Hardware, AI/Bot, Script.
- Project Detail: Description, AI contribution, screenshots, actions.
- Dev Logs: Links or summaries from each project.

**Recommended Actions**
- `Install` for APK downloads.
- `View Source` for GitHub links.
- `View Hardware` for projects that require devices.
- `Clone Architecture` for bots and agent projects.
- `Run Script` for script-based tools.

**Notes**
- Treat the manifest as the single source of truth.
- Keep the UI kit stable so the ecosystem looks like one product.
