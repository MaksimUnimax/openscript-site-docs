# Module map — OpenScript / AI Starter Community

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

This file is the current module map for the site project.
Detailed snapshots are under docs/codex_source/module_map/imported/.

## Source-derived module map

Based on tracked source files in /opt/ai-starter-community/source/app/:

### Core modules (implemented, source-proven)
- app/core/ — FastAPI app factory, env config, health endpoints
- app/main.py — Application entrypoint (create_app)
- app/shared/ — Database helpers, password/security utils, shared templates
- app/auth/ — Registration, login, email verification, password reset, cookie sessions
- app/public_landing/ — Public landing page
- app/materials/ — Course content with lessons and materials
- app/user_cabinet/ — User cabinet with settings and private files
- app/admin/ — Admin panel with tariff/option CRUD, user management, CLI bootstrap
- app/tariffs/ — Product tariff schemas and service
- app/paid_options/ — Paid option schemas and service
- app/notifications/ — Email outbox and SMTP adapter

### Modules with structure only (implementation NOT_YET_PROVEN)
- app/payments/ — Directory exists with __init__.py only
- app/ai_sales_agent/ — Directory exists with __init__.py only

### Test modules (source-proven)
- tests/test_auth_flow.py — Auth end-to-end test
- tests/test_admin_access.py — Admin access control test
- tests/test_admin_bootstrap_cli.py — Bootstrap CLI test
- tests/test_admin_catalog_services.py — Catalog services test
- tests/test_admin_paid_option_crud_ui.py — Paid option CRUD
- tests/test_admin_readonly_lists.py — Read-only admin lists
- tests/test_admin_role_management.py — Role management
- tests/test_admin_tariff_crud_ui.py — Tariff CRUD
- tests/test_admin_tariff_option_linking_ui.py — Tariff-option linking
- tests/test_admin_user_filters.py — User filters
- tests/test_cabinet_catalog_display.py — Cabinet catalog display
- tests/test_catalog.py — Catalog display
- tests/test_clean_active_skills.py — Clean active skills
- tests/test_context_navigation.py — Context navigation
- tests/test_course_content_lesson_01.py — Lesson rendering
- tests/test_course_rendering.py — Course rendering
- tests/test_dair_lesson_generator_skill.py — DAIR skill
- tests/test_email_delivery.py — Email delivery
- tests/test_health.py — Health endpoint
- tests/test_materials_flow.py — Materials flow
- tests/test_mblode_active_skill_complete.py — MBLODE skill
- tests/test_module_registration.py — Module registration
- tests/test_routes.py — Route registration
- tests/test_static_assets.py — Static asset serving

## Safe boundaries

- source/app/ is application code — changes require staging/test environment
- runtime/, state/, logs/, backups/, tmp/ are NOT source of truth
- .env files and secrets are gitignored and must never be read
- Docs are maintained in /opt/openscript-site-docs, not in the app repo
- App repo changes must be proven against staging before any push to feature branch

## Detailed snapshot

See docs/codex_source/module_map/imported/current_module_map_snapshot.md for the full source-derived detailed map.

## 2026-06-03 — Course lessons 1–9 semantic blocks accepted

### Append id

- MM_SITE_COURSE_LESSONS_20260603

### Current module-state note

- App module affected: `app/materials` / course content draft
- Target file: `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- Final accepted implementation:
  - course has lessons 1–9;
  - each lesson has semantic blocks in data;
  - renderer supports `section.blocks` through `renderLessonBlocks`;
  - old `contentHtml` fallback remains;
  - lesson 4 starter prompt controls remain;
  - copy/download buttons remain visible;
  - prompt textarea is hidden by default;
  - deploy-key logic is visible and corrected.
- Boundaries:
  - no production runtime changes;
  - no Agent Lab changes;
  - no app runtime/state changes recorded in this docs update;
  - this docs update does not modify the app repo.

## 2026-06-05 — Course lesson 7 rewrite accepted; design preflight ready

### Append id

- MODULE_MAP_SITE_20260605_STAGING_AND_COURSE_STATE_SYNC

### Current module-state note

- `source/app/materials/course_content/drafts/dair_smoke_20260529/` is the current course draft area for "Работа с ИИ".
- Lesson 7 current title is `Процесс работы`.
- `staging/` remains the app repo support directory for local design/test runtime.
- `staging/start.sh` starts localhost-only staging.
- `staging/env.staging.example` contains non-secret local env defaults.
- `staging/data/**` and `staging/runtime/**` are runtime/generated/ignored except `.gitkeep`.
- `source/app/**` remains app source; `source/tests/**` remains test source.
- Agent Lab repos are not part of the site module map for current site workflow.
- The next run is proof-only design workflow preflight; no UI patch yet.

## 2026-06-04 — Course lessons 5 and 6 swap accepted

### Append id

- MM_SITE_COURSE_LESSONS_20260604_SWAP

### Current module-state note

- App module affected: `app/materials` / course content draft
- Target file: `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- Accepted app commit: `daaa8fcd84d448b94c0f16b5302c90086251b9ac`
- Final accepted implementation:
  - course lesson order remains 1–9;
  - lesson 5 is now `Codex, AGENTS.md, Skills, токены и роль модели`;
  - lesson 6 is now `PowerShell, Terminal и подключение к серверу`;
  - lesson 5 content is fully rewritten for the Codex lesson;
  - lesson 6 content is the terminal/server lesson with updated navigation and checks;
  - the current app docs and course map must reflect this accepted state.
- Boundaries:
  - no production runtime changes;
  - no Agent Lab changes;
  - no app runtime/state changes recorded in this docs update;
  - this docs update does not modify the app repo.
