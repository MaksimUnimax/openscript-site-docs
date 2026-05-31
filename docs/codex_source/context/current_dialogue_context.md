# Current dialogue context — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531

This file is append-only.

Do not rewrite historical blocks destructively.

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_INITIAL_SOURCE_BASELINE source=codex_sync -->
## 2026-05-31 — Initial source-derived documentation baseline imported

This run imported the first source-derived documentation baseline for the OpenScript / AI Starter Community site project.

### Documentation created/updated

- project/current_status.md — site-specific current status
- project/technical_spec.md — initial source-derived technical spec
- module_map/module_map.md — site-specific module map
- module_map/module_map_manifest.yaml — site manifest
- module_map/imported/current_module_map_snapshot.md — detailed module snapshot
- roadmap/roadmap_manifest.yaml — site roadmap manifest
- roadmap/imported/roadmap_v0_1_initial_site_baseline.md — initial roadmap
- project/safe_boundaries.md — site-specific safe boundaries
- project/source_vs_runtime.md — site-specific source vs runtime rules
- project/import_queue/missing_sources.yaml — site-specific missing items
- context/context_manifest.yaml — updated for site
- context/current_dialogue_context.md — this append block

### Source-derived facts

- Stack: FastAPI + Jinja2 + SQLite + bcrypt + uvicorn
- All implemented modules: core, auth, admin, landing, materials, cabinet, tariffs, paid_options, notifications, shared
- Structure-only modules: payments, ai_sales_agent (NOT_YET_PROVEN)
- Auth includes registration (currently closed), email verification, cookie sessions, password reset
- App on branch design/product-story-03, 9 untracked files

### Next step

Design and create a staging/test environment before any app source changes.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_INITIAL_SOURCE_BASELINE -->
