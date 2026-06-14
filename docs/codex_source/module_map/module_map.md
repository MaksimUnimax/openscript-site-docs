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

## 2026-06-09 — Cabinet account-blocks and paid-options live iteration

### Append id

- MODULE_MAP_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION

### Current module-state note

- `app/user_cabinet/` now includes the server-backed cabinet account-blocks flow.
- `app/account_blocks/` is implemented and provides the account block backend/service.
- `app/admin/` includes moderator assignment for `users.role` and keeps admin-only dashboard access.
- `app/notifications/` includes activation email wiring for account blocks through the existing outbox/SMTP adapter layer.
- `app/paid_options/` remains the paid-option catalog layer; the cabinet now shows the active add-on activation block.
- `app/shared/db.py` now includes the `account_blocks` table schema support.
- `source/app/static/cabinet-local-accounts.js` no longer acts as the source of truth for server-backed account blocks.
- `source/app/user_cabinet/templates/cabinet.html` renders the no-jump account action flow and bounded-width account cards.
- `source/app/static/styles.css` bounds the account card grid so a single card does not stretch full width on desktop/tablet.
- Legacy localStorage account-block behavior is not the current site memory.
- Payment processing remains NOT_YET_PROVEN even though the paid-options cabinet block is live.
- Password-secret encryption policy remains open.
- Manual browser verification of the latest no-jump/card-width/account-email behavior is still pending unless explicitly confirmed by the user.

### Boundaries

- no production runtime changes in this docs update;
- no Agent Lab changes;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

## 2026-06-14 — Admin course export and course lesson 4/5 accepted

### Append id

- MODULE_MAP_SITE_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED

### Current module-state note

- `app/materials/` now reflects the accepted lesson 4 title `Codex, AGENTS.md, токены и роль модели`.
- Lesson 4 visible content no longer includes `Skills`, `Skill`, `/skills`, `plugins`, `plugin`, or `/plugins`.
- Lesson 4 uses approved `рабочий шаг (run)` terminology, `лимиты ресурсов`, and the three slash commands `/status`, `/model`, and `/permissions`.
- `app/materials/` lesson 5 now links `личный кабинет курса` and grammatical variants to `https://openscript.ru/cabinet` with `target="_blank"` and `rel="noreferrer"`.
- `app/admin/course_export.py` now source-drives the export of all referenced static carousel assets, hero images, and the three prompt markdown files.
- `tests/test_admin_course_export.py` covers the accepted export asset/prompt/manifest behavior.
- `tests/test_course_rendering.py` covers the accepted lesson 4/5 rendering expectations.
- Accepted export facts:
  - 72 ZIP entries total;
  - 51 carousel assets;
  - 2 hero images;
  - 3 prompt markdown files;
  - sanitized `manifest.json` with no absolute server paths.
- Prompt file paths:
  - `prompts/01-start-project-documentation.md`
  - `prompts/02-project-docs-update.md`
  - `prompts/03-new-project-dialogue.md`

### Boundaries

- no production runtime changes in this docs update;
- no Agent Lab changes;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

## 2026-06-10 — Course carousels and VPN account-block iteration

### Append id

- MODULE_MAP_SITE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION

### Current module-state note

- `app/materials/` now carries the course practice-carousel pattern used by the current course memory update.
- The lesson 3 Git practice uses a real screenshot carousel sourced from static course assets.
- The remaining practical lessons keep placeholder carousel instances for the click-based course method.
- The lesson 6 project-start carousel was added after the first pass missed it.
- `app/user_cabinet/` now includes the restored 4/2/1 account grid, real VPN block rendering, VPN video panel, and the account-card title wrap fix.
- `app/account_blocks/` now includes VPN type support and the validation rule that blank login/password fields are not required for VPN.
- `source/app/static/course-assets/dair-smoke-20260529/git-carousel/*.png` and `source/app/static/videos/amnezia-vpn-guide.mp4` are the relevant static asset families for this current memory state.
- The polished VPN panel with Tech Talk attribution and the normal-sized Amnezia button is reported as feature/live-synced state; if not already fast-forwarded into the active branch, treat it as pending branch integration.
- The requested separate collapsible VPN block after Accounts is pending/not yet proven.
- `app/payments/` remains NOT_YET_PROVEN.

### Boundaries

- no production runtime changes in this docs update;
- no Agent Lab changes;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.
