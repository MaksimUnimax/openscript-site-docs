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
<!-- MODULE_MAP_APPEND_BEGIN id=MODULE_MAP_SITE_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED source=codex_sync -->
## 2026-06-17 — Phase 1 password-secret encryption source support accepted

### Current module-state note

- `app/account_blocks/secret_crypto.py` is the new narrow helper that handles authenticated symmetric encryption envelopes for `password_secret`.
- `app/account_blocks/` now stores new and updated non-empty password secrets as encrypted envelopes and decrypts them on authorized read paths.
- `app/core/` now exposes the `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY` runtime setting used by the account-block secret helper.
- `source/tests/conftest.py` now provides the deterministic test key fixture support used by the account-block encryption tests.
- `tests/test_account_blocks_service.py`, `tests/test_account_blocks_admin_ui.py`, and `tests/test_account_blocks_cabinet_ui.py` now cover encrypted storage, legacy plaintext compatibility, and safe missing/wrong-key behavior.
- `source/pyproject.toml` and `source/uv.lock` now include the `cryptography` dependency required for AES-GCM.
- Phase 2 migration of already stored plaintext rows remains open.

### Boundaries

- no production runtime changes in this docs update;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

<!-- MODULE_MAP_APPEND_END id=MODULE_MAP_SITE_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED -->

<!-- MODULE_MAP_APPEND_BEGIN id=MODULE_MAP_SITE_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED source=codex_sync -->
## 2026-06-17 — Password-secret Phase 2 preview DB migration completed

### Current module-state note

- `app/account_blocks/secret_crypto.py` remains the narrow helper that handles authenticated symmetric encryption envelopes for `password_secret`.
- `app/account_blocks/` now stores/decrypts encrypted envelopes in the preview DB, and the preview plaintext rows were migrated to `enc:v1:` envelopes.
- `app/core/` still exposes the `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY` runtime setting used by the account-block secret helper.
- `source/tests/conftest.py` still provides the deterministic test-key fixture support used by the account-block encryption tests.
- `tests/test_account_blocks_service.py`, `tests/test_account_blocks_admin_ui.py`, and `tests/test_account_blocks_cabinet_ui.py` still cover encrypted storage, legacy plaintext compatibility, and safe missing/wrong-key behavior.
- `source/pyproject.toml` and `source/uv.lock` still include the `cryptography` dependency required for AES-GCM.
- The preview runtime venv was synced with `cryptography==49.0.0` and runtime deps because it initially lacked the dependency needed by the Phase 1 source support.
- Phase 2 migration of already stored plaintext rows is now complete in preview.

### Boundaries

- no production runtime changes in this docs update;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.
<!-- MODULE_MAP_APPEND_END id=MODULE_MAP_SITE_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED -->

<!-- MODULE_MAP_APPEND_BEGIN id=MODULE_MAP_SITE_20260617_CSRF_SOURCE_FIX_ACCEPTED source=codex_sync -->
## 2026-06-17 — CSRF source fix accepted

- `app/shared/csrf.py` now centralizes browser-form CSRF token generation and validation.
- `app/auth/`, `app/admin/`, `app/user_cabinet/`, and `app/public_landing/` templates now render the hidden `_csrf_token` field for state-changing browser forms.
- Unsafe browser POST handlers now reject missing or invalid CSRF tokens with HTTP 403.
- The protected browser-form surface covers login, logout, register, resend verification, forgot/reset password, admin user/material/tariff/account-block forms, cabinet settings/account-block forms, and public landing forms.
- `tests/test_csrf_protection.py` adds dedicated coverage for missing-token, invalid-token, valid-token, and GET/read-only behavior.
- The updated browser-flow tests still pass for the account-block and auth routes.
- The CSRF source fix is source-only; no runtime deployment or preview rollout is claimed in this docs update.
- The next security follow-up remains `change_password()` session revocation behavior.
<!-- MODULE_MAP_APPEND_END id=MODULE_MAP_SITE_20260617_CSRF_SOURCE_FIX_ACCEPTED -->
<!-- MODULE_MAP_APPEND_BEGIN id=MODULE_MAP_SITE_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED source=codex_sync -->
## 2026-06-17 — Post-CSRF emergency fixes and materials public preview accepted

### Current module-state note

- `app/auth/` now includes the session-revocation behavior on password change (`e7fc37d272ca136418dd7e3a175cbbfb5bb03f96`), and successful password change clears the current browser session.
- `app/public_landing/` now uses the corrected template helper path from `55ad86e6e1ff6b8dd7fbf015fd8e46e72390fa10` so `/` renders without the duplicate-request TypeError.
- `app/admin/` runtime proof required a controlled restart of `ai-starter-community-preview.service` so the live Jinja environment loaded the CSRF helper used by admin templates.
- `app/materials/` now registers the shared CSRF helper, and the authenticated draft page no longer fails on `csrf_input`.
- `app/materials/` also carries the gated public preview allowlist for the selected staging draft paths from `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928`; the bypass is disabled by default, GET/HEAD only, and leaves non-allowlisted materials protected.
- `source/tests/test_materials_flow.py` and `source/tests/test_routes.py` now cover the current materials/public-landing safety behavior.
- The preview runtime smoke proof reached 30 GET URLs with `TOTAL_5XX` `0`.
- `source/app/materials/routes.py` is clean after the gated public preview commit.
- `app/shared/csrf.py` remains the shared CSRF helper for browser forms.
- The session-revocation app run had a strict pre-edit backup gate violation, but no rollback was performed and the source fix remains accepted.

### Boundaries

- no production runtime changes in this docs update;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

<!-- MODULE_MAP_APPEND_END id=MODULE_MAP_SITE_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED -->

## 2026-06-15 — Public tariff/access UI iteration accepted

### Current module-state note

- `app/admin/` tariff CRUD now includes same-page edit save notices and safe integer typography controls.
- `app/tariffs/` tariff rows now carry `show_on_homepage`, `pricing_text_align`, `title_font_size_px`, `price_font_size_px`, and `description_font_size_px`.
- `app/shared/` tariff display helper and pricing partial render selected tariff cards with safe CSS custom properties and font-size-aware rows.
- `app/user_cabinet/` the shared selected-tariff block remains the cabinet surface for tariff/access UI and continues to show up to two selected tariffs in source-backed order.
- `source/app/static/styles.css` owns the selected tariff typography variables and row sizing that prevents overlap at larger font sizes.
- `app/public_landing/` and `app/user_cabinet/` continue to consume the shared pricing surface; source-backed order and alignment remain intact.
- Real payment remains NOT_YET_PROVEN.

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

## 2026-06-16 — Isolated course editor version manager repaired and restored

### Append id

- MODULE_MAP_SITE_20260616_ISOLATED_COURSE_EDITOR_VERSION_MANAGER_REPAIR

### Current module-state note

- `staging/course-editor/current/` is isolated editor tooling/runtime under the app repo staging path, not app source.
- The active editor version registry lives at `staging/course-editor/current/versions/index.json`.
- Managed versions are stored under `staging/course-editor/current/versions/`.
- The working copy lives under `staging/course-editor/current/work/`.
- Editor exports live under `staging/course-editor/current/exports/` and are runtime/recovery artifacts, not app source.
- `/tmp/course-editor-version-uploads/` and `/tmp/openscript-universal-method-course-*.zip` are source ZIP recovery artifacts, not app source.
- Real delete tests must not target real course versions.

### Current module-state summary

- The editor dropdown/list was restored to `current`, `v01`, `v02`, `v03`, `edited`, and `v04`.
- The mistaken deletion test had reduced the registry to only `v001 / current`.
- The restore was explicitly approved after that mistake and scoped only to the isolated editor registry/list.
- The restore used safe ZIP sources only and did not touch production, app source, or Agent Lab.

### Boundaries

- docs-only updates must not touch `/opt/ai-starter-community/staging/course-editor/current/**`
- app source `/opt/ai-starter-community/source/app/materials/course_content/**` remains forbidden unless explicitly approved
- production remains forbidden

## 2026-06-17 — P0 auth hardening source fix accepted

### Append id

- MODULE_MAP_SITE_20260617_P0_AUTH_HARDENING_SOURCE_FIX_ACCEPTED

### Current module-state note

- `app/auth/` now includes login brute-force protection in `authenticate_user(...)`.
- `app/core/` now defaults session cookies secure in production-like environments while preserving an explicit env override for local/dev.
- `app/auth/routes.py` continues to use `settings.session_cookie_secure` when setting the login session cookie.
- `tests/test_auth_flow.py` now covers the non-enumerating login error path, the login rate limit, the successful-login reset path, and the secure-cookie default/override behavior.
- The login limiter is process-local in memory and is not the final shared-store design.

### Security follow-up

- `password_secret` encryption remains open and should be handled as a separate design/proof run with a DB/state backup gate.

### Boundaries

- no production runtime changes in this docs update;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

<!-- MODULE_MAP_APPEND_BEGIN id=MODULE_MAP_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED source=codex_sync -->
## 2026-06-17 — SQLite WAL / busy_timeout source fix accepted, runtime apply pending

### Current module-state note

- `app/shared/db.py` now centralizes SQLite connection hardening with a shared helper.
- `source/app/shared/db.py` defines `SQLITE_BUSY_TIMEOUT_MS = 5000`.
- File-backed app SQLite connections now apply `PRAGMA busy_timeout = 5000`, `PRAGMA foreign_keys = ON`, and `PRAGMA journal_mode = WAL`.
- In-memory SQLite databases skip WAL and parent-directory creation safely while still getting busy timeout and foreign-key setup.
- `source/tests/test_db_connection_pragmas.py` covers the WAL/busy_timeout behavior on temp file-backed DBs and in-memory DBs.
- The accepted app source commit is `3ffd6c9ec2af4b585d94479259c7770c21ce6778`.
- The running preview process has not yet been restarted or reloaded for this source fix.
- Live DB was not touched in the source run, and no manual live SQLite PRAGMA was executed.

### Boundaries

- first future runtime apply/restart is backup-gated because WAL activation can mutate SQLite state and create WAL-related sidecar files;
- manual live DB PRAGMA is not required by the source fix;
- no production runtime changes in this docs update;
- no Agent Lab changes;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

<!-- MODULE_MAP_APPEND_END id=MODULE_MAP_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED -->
<!-- MODULE_MAP_APPEND_BEGIN id=MODULE_MAP_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED source=codex_sync -->
## 2026-06-17 — SQLite WAL / busy_timeout runtime applied accepted

### Current module-state note

- `source/app/shared/db.py` is now active in preview runtime via the restarted app service.
- `SQLITE_BUSY_TIMEOUT_MS = 5000` is live for new app-style SQLite connections.
- File-backed app SQLite connections now apply `PRAGMA busy_timeout = 5000`, `PRAGMA foreign_keys = ON`, and `PRAGMA journal_mode = WAL` in the preview runtime.
- After restart, the live state directory contains `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm`.
- An app-style connection through `source/app/shared/db.py:get_connection()` reported `busy_timeout = 5000`, `journal_mode = wal`, and `foreign_keys = 1`.
- The runtime apply used the DB/state backup gate before restart and did not require a manual live PRAGMA.
- The preview service restarted successfully and remained active running.
- The smoke proof after restart reported `TOTAL_5XX: 0`.
- No new `database is locked` errors or tracebacks were observed after restart.

### Boundaries

- no source modification in this docs update;
- no runtime modification in this docs update;
- no app repo modification;
- no Agent Lab changes;
- no app runtime/state changes recorded in this docs update;
- this docs update does not modify the app repo.

<!-- MODULE_MAP_APPEND_END id=MODULE_MAP_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED -->
