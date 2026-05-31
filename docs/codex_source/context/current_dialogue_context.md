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

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_STAGING_IMPLEMENTATION source=codex_sync -->
## 2026-05-31 — Staging environment implemented

### App repo changes

- .gitignore — added staging/data/* and staging/runtime/* ignore rules
- staging/start.sh — staging startup script (bash -n validated)
- staging/env.staging.example — non-secret env var template
- staging/README.md — staging usage and safety instructions
- staging/data/.gitkeep — placeholder for isolated SQLite database
- staging/runtime/.gitkeep — placeholder for isolated runtime files

### Docs repo changes

- project/staging_environment.md — staging environment description
- project/staging_proof.md — staging isolation proof
- project/safe_boundaries.md — updated with staging paths
- project/source_vs_runtime.md — updated with staging layer
- project/current_status.md — updated with staging status
- project/import_queue/missing_sources.yaml — staging items marked done
- context/context_manifest.yaml — updated append tracking
- context/current_dialogue_context.md — this append block

### Key facts

- Staging created with zero core source code changes (env-driven config only).
- Staging binds to 127.0.0.1:8090 with isolated SQLite database.
- start.sh was NOT executed — staging is not running.
- No production runtime touched.
- Agent Lab repos untouched.

### Current blocker

Staging is created but has NOT been started or verified.
Next safe step: start staging locally and verify /healthz endpoint.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_STAGING_IMPLEMENTATION -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_HEALTH_PROOF source=codex_sync -->
## 2026-05-31 — Staging health proof successful

### Health check results

- start.sh was fixed to use source/.venv/bin/python (project virtual environment)
- Staging started on 127.0.0.1:8090
- Listener confirmed on 127.0.0.1:8090 only
- /healthz returned: {"ok":true,"service":"ai-starter-community"}
- /readyz returned: {"ok":true,"ready":true}
- Staging process stopped after health check
- Port 8090 confirmed free after stop

### Files changed

- staging/start.sh — added virtual environment detection (committed and pushed)
- project/staging_proof.md — updated PROVEN_RUNTIME
- project/current_status.md — updated healthy status
- context/current_dialogue_context.md — this append block
- context/context_manifest.yaml — updated append tracking

### Key facts

- No source/app/** changed
- No source/tests/** changed
- No production state/runtime/logs/backups changed
- Agent Lab repos untouched
- Staging is ready for design/Kilo workflow runs
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_HEALTH_PROOF -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260531_SYNC source=codex_sync -->
## 2026-05-31 — Docs synchronized after staging health proof

### Files updated in this sync

- project/current_status.md — updated HEAD to 6fae69f, added completed runs, added current active block, decisions, open questions
- roadmap/roadmap_manifest.yaml — updated phases: Stage 2 completed, Stage 3 active (Design/Kilo)
- roadmap/imported/roadmap_v0_1_initial_site_baseline.md — restructured to 6 stages, Stage 2 marked health-proven
- project/source_vs_runtime.md — added staging support scripts as source of truth
- project/import_queue/missing_sources.yaml — updated staging items to health-proven, added Kilo workflow config placeholder
- context/context_manifest.yaml — updated append tracking
- context/current_dialogue_context.md — this append block

### Current active block

Design/Kilo workflow for OpenScript / AI Starter Community through proven staging/test contour.

### Roadmap stages

- Stage 0 — Repo separation and AGENTS bootstrap: COMPLETED
- Stage 1 — Site docs currentization and source-derived baseline: COMPLETED
- Stage 2 — Isolated staging/test contour: COMPLETED and HEALTH-PROVEN (healthz/readyz on 127.0.0.1:8090)
- Stage 3 — Design/Kilo workflow on staging: NEXT
- Stage 4 — Manual review and screenshot proof: LATER
- Stage 5 — Production handoff: LATER, separate approval required

### Not next

- Production deploy
- Payment implementation
- AI Sales Agent implementation
- Agent Lab work
- Docs cleanup of Agent Lab
- App refactor
- nginx/systemd
- Public staging exposure
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260531_SYNC -->
