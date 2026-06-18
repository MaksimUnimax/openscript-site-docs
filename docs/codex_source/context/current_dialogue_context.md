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

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_COURSE_LESSONS_20260603 source=codex_sync -->
## 2026-06-03 — Course lessons 1–9 semantic blocks accepted

This run currentized the site/course dialogue state after the accepted course lesson refinement work.

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03

### Final accepted app state

- Latest accepted app commit: a5a2f6ef40338959a659bc9feecf0a23c46a0c70
- Commit title: Add semantic lesson blocks
- Changed file: source/app/materials/course_content/drafts/dair_smoke_20260529/script.js
- Public GitHub showed 1 file changed, 916 additions, 10 deletions
- Previous accepted app commit immediately before the final block split: a7458df00e3b42b09cfcdffae1d14e90be43f028

### Accepted course implementation facts

- Lessons 1–9 are now split into semantic blocks/cards.
- `renderLessonBlocks` supports `section.blocks` as `callout lesson-content-block` cards.
- Fallback to old `contentHtml` remains for lessons without blocks.
- Lesson 4 keeps the starter prompt controls:
  - Перейти к стартовому prompt
  - Смотреть prompt
  - Скопировать prompt
  - Скачать .md
- Copy/download buttons remain visible.
- Only the prompt textarea is hidden/collapsed by default.
- Lesson 4 deploy-key wording was corrected so the private key stays on the server, the public key goes to GitHub Deploy keys, and the user returns with confirmation only.
- `starterPromptMarkdown` formatting was intentionally not repaired in the accepted final app run.

### Current stop-point

Course lesson semantic-block UI/content pass is accepted by the user.
Docs update is now required to bring the public docs repo current.

### Next safe step

Wait for the user-selected next task after this docs update.
Do not resume the old Kilo/design workflow automatically.

### Historical correction

Any older Kilo/design workflow references are historical unless the user explicitly chooses Kilo.
<!-- CONTEXT_APPEND_END id=CTX_SITE_COURSE_LESSONS_20260603 -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY source=codex_sync -->
## CTX_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY

- Public docs were stale relative to accepted app course work.
- Course lesson refinement is accepted through app commit f6f5c2b100296efd69c67fa7387550cf2595340d.
- Lesson 7 was renamed to "Процесс работы" and now covers run types, control of Codex, context window, and prefix-extension practice.
- Staging/test contour remains proven and localhost-only.
- Next user-selected technical direction is Design/Kilo workflow preparation.
- The next run must be proof-only preflight and must not patch UI yet.
- Agent Lab remains no-touch.
- Production remains no-touch.
- No secrets may be read.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260608_SITE_DOCS_CURRENT_STATE_SYNC source=codex_sync -->
## 2026-06-08 — Site docs current-state sync verified from local source

### Verified app course baseline

- `source/app/materials/course_content/drafts/dair_smoke_20260529/index.html`
- `source/app/materials/course_content/drafts/dair_smoke_20260529/script.js`
- `source/tests/test_course_rendering.py`
- accepted app commit: `f6f5c2b100296efd69c67fa7387550cf2595340d`
- current lesson 7 title: `Процесс работы`

### Verified current course facts

- course has 9 lessons;
- lesson 7 covers `run`, `design run`, `fix run`, `proof run`, `context`, `context window`, and `prefix`-extension practice;
- lesson 7 includes a starter prompt panel with copy/download actions and a readonly textarea preview;
- lesson 6 has the starter prompt panel for project documentation start;
- lesson 8 has starter prompt panels for docs update and new dialogue;
- no visible lesson 10 exists in the current source.

### Docs repair result

- stale uppercase current status, roadmap, lesson map, materials spec, course method spec, and decisions were synchronized to the current lesson 7 state;
- legacy Agent Lab / YouTube bridge docs were marked as legacy/imported, not current site state;
- current safe next app step remains the proof-only design workflow preflight;
- no app source was changed.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260608_SITE_DOCS_CURRENT_STATE_SYNC -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR source=codex_sync -->
## 2026-06-08 — Course order and final section repaired from source

### Verified current source truth

- Lesson 4: `Codex, AGENTS.md, Skills, токены и роль модели`
- Lesson 5: `PowerShell, Terminal и подключение к серверу`
- Lesson 6: `Старт проекта: сначала документация, потом разработка`
- Lesson 7: `Процесс работы`
- Final section: `lesson-10` / `Финал курса`

### Verified current course wording

- The course has 9 numbered lessons plus a visible final section.
- Lesson 6 owns the starter prompt for project documentation start.
- Lesson 7 owns the starter prompt for prefix-extension practice.
- Lesson 8 owns the starter prompts for docs update and new dialogue.

### Repair result

- Previous course-order statements that treated 4/5/6 as start project / Codex / PowerShell are superseded.
- Previous wording that said there was no visible lesson 10 is superseded.
- Current docs should use the 9 numbered lessons plus final section wording.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260608_COURSE_ORDER_AND_FINAL_SECTION_REPAIR -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION source=codex_sync -->
## 2026-06-09 — Cabinet account-blocks and paid-options live iteration

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- Public docs repo: https://github.com/MaksimUnimax/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community
- App branch: design/product-story-03

### Verified live state from the latest app reports

- Paid-options cabinet block is live and shows active add-ons from the database.
- The base AI / GPT tool option is hidden from the add-on activation block.
- Add-ons are ordered by price descending.
- The buy button remains a safe placeholder; real payment processing is still not implemented.
- Server-backed account blocks are live in `/cabinet`.
- LocalStorage is no longer the source of truth for account blocks.
- Account block types supported in UI: ChatGPT, Сервер, Почта.
- Owner is resolved server-side and hidden from the visible UI.
- Manual title and email inputs were removed from the account block UI.
- Admin and moderator can create, edit, delete, and activate account blocks.
- Moderator does not gain full admin dashboard rights.
- Activation email is wired to the owner user's registered email.
- Activation text uses elapsed-day wording, not remaining-days wording.
- Account actions use fetch-based no-jump handling and preserve scroll position.
- Account cards use bounded tracks and do not stretch full width on desktop/tablet when only one card is visible.
- Production test-user cleanup was completed with a backup before deletion.

### Accepted live-source commits

- `f10fb8efd2b2d044f66122952675ee66cc0dbd3d` — paid-options hide-base/sort/alignment live deploy
- `3e45d12c1807eae877065459a5c68f762ef02da1` — account_blocks backend/service foundation
- `a16ab80cf354ddfe1a3b48e3d5ee52e716c9b00c` — server-backed cabinet UI and admin/moderator management
- `f67ef013eb831ec76ce3cf69eca40fc8da19d0a8` — moderator assignment for users.role
- `da3ce7f939bffe1cbb802048964c83aae96214a9` — compact card UI and elapsed activation status
- `1a89fd5eea26e955b4f2fe33cfb6e13cf44f3201` — owner selector / action form fixes
- `a3bd97243a267691c6d06403223a470c2fafdefb` — activation email import-cycle/runtime fix
- `7c94211819ddb334575d7835152637972930d393` — no-jump account actions and bounded account card width

### Manual verification status

- Manual browser verification of the latest no-jump/card-width/account-email behavior is still pending unless explicitly confirmed by the user.
- This docs update records the technical deployed state only.
- Real payment processing remains NOT_YET_PROVEN.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION source=codex_sync -->
## 2026-06-10 — Course carousels and VPN account-block iteration

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: design/product-story-03

### Current active block

- `course_practice_carousels_and_vpn_account_block_iteration`

### Completed / proven since the last saved site docs point

1. Course practical carousels are now part of the current course memory.
- Lesson 3 Git uses a real screenshot carousel from static course assets.
- The Git carousel image delivery moved to `/static/course-assets/dair-smoke-20260529/git-carousel/`.
- Slide sizing, labels, and the first slide label were polished.
- Placeholder carousels were added for remaining practical lessons.
- Lesson 6 project-start carousel was initially missed and then fixed.
- Lesson 7 prefix-extension practice keeps a placeholder carousel pattern.
- Lesson 8 docs update / new-dialog workflow uses the same placeholder carousel pattern when present in source.

2. VPN is now a real account-block type in the cabinet memory.
- VPN is server-backed, not hardcoded.
- VPN does not require login/password.
- The 4-column desktop / 2-column tablet / 1-column mobile grid was restored.
- ChatGPT title wrapping was fixed in the cabinet panel.
- VPN video asset is served from `/static/videos/amnezia-vpn-guide.mp4`.
- The polished VPN panel adds Tech Talk attribution and a normal-sized Amnezia VPN button in the reported feature/live-synced state.
- If `fbb1477a69ee517ff30736326617e5d4b914b320` has not yet been fast-forwarded into the active branch, treat that polish as pending branch integration instead of accepted mainline state.

### Current pending user task

- Move VPN into a separate collapsible block after Accounts.
- Remove the crossed-out instruction line from the VPN block.
- Keep the video inside the collapsible content.
- This request is pending/not proven unless a later report explicitly confirms it.

### Open / not current

- Real payment remains NOT_YET_PROVEN.
- Password-secret encryption policy remains open.
- Manual browser verification of the latest course carousel and VPN behavior is still required unless explicitly confirmed by the user.
- Agent Lab docs remain legacy / no-touch and are not the current site corpus.

### Not next

- Do not treat the separate collapsible VPN block as completed until it is proven.
- Do not move into payment or production work from this docs update.
- Do not use Kilo/design as the current active task unless the user explicitly selects it.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED source=codex_sync -->
## 2026-06-14 — Course lesson 4/5 polish and admin ZIP export accepted

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: design/product-story-03

### Accepted app facts recorded here

- `a6c0b277b6e6c35def432cf26b630dd02b161a77` — lesson 4 terminology and lesson 5 cabinet link polished
- `cf23dda5585e176d9be0075d5e47e557d1ec309d` — all referenced course assets included in export
- `56d3f0a1a6be067ea1178f3ef3516fe7ff142a0f` — course prompt files exported and manifest sanitized

### Accepted course facts

- Lesson 4 title is `Codex, AGENTS.md, токены и роль модели`.
- Lesson 4 no longer shows `Skills`, `Skill`, `/skills`, `plugins`, `plugin`, or `/plugins` in accepted visible content.
- Lesson 4 uses approved `рабочий шаг (run)` wording and `лимиты ресурсов`.
- Lesson 4 slash-command section now teaches `/status`, `/model`, and `/permissions` with the slash-menu explanation.
- Lesson 5 links `личный кабинет курса` and grammatical variants to `https://openscript.ru/cabinet` with `target="_blank"` and `rel="noreferrer"`.

### Accepted export facts

- Admin course export route: `/admin/course-export`
- ZIP export totals: 72 entries, 51 carousel assets, 2 hero images, 3 prompt markdown files
- Manifest is sanitized and does not leak absolute server paths
- Prompt files exported:
  - `prompts/01-start-project-documentation.md`
  - `prompts/02-project-docs-update.md`
  - `prompts/03-new-project-dialogue.md`

### Current stop-point

Course lesson 4/5 wording and the admin course ZIP export are accepted. The next safe step is the next explicit user-selected task. Do not start payment, production, Agent Lab, or broad app refactor automatically.

### No app-source change here

- This docs update did not modify `/opt/ai-starter-community`.
- This docs update is docs-only and append-only.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260615_PUBLIC_TARIFF_ACCESS_UI_ITERATION_ACCEPTED source=codex_sync -->
## 2026-06-15 — Public tariff/access UI iteration accepted

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: fix/carousel-arrow-button-visuals

### Current active block

- `public_tariff_access_ui_iteration_accepted`

### Accepted live-state facts

- Latest accepted/deployed app commit: `eb22b091a2a732966c62e24a93c1799babc3440f` — Keep tariff edit page and scale card typography
- Earlier typography-control commit: `8a905300739c833ee46ad06383a76d6e65e1c489` — Add tariff typography controls
- Tariff admin now supports source-backed order, selected-card alignment, and safe integer px typography controls
- Tariff edit save stays on the same edit page with the success notice `Изменения сохранены.`
- New tariff creation redirects to the new tariff edit page with the success notice `Тариф создан.`
- Selected tariff cards render through the shared pricing partial and safe CSS variables so large typography does not overlap the description
- Public/authenticated UI and cabinet access-gate recovery remain part of the accepted live state
- Real payment remains NOT_YET_PROVEN

### Current stop-point

- The latest public tariff/access/UI iteration is accepted and deployed. Next safe step is the next explicit user-selected task.
- Do not infer payment or Agent Lab work automatically.
- This docs update is append-only and docs-only.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260615_PUBLIC_TARIFF_ACCESS_UI_ITERATION_ACCEPTED -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260616_ISOLATED_COURSE_EDITOR_VERSION_MANAGER_REPAIR source=codex_sync -->
## 2026-06-16 — Isolated course editor version manager repaired and restored

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community

### Isolated editor

- Editor URL: http://80.74.29.249:8092/
- Editor root: /opt/ai-starter-community/staging/course-editor/current/
- Editor process reported: `python /opt/ai-starter-community/staging/course-editor/current/server.py`
- Current reported PID after restore: `2793406`
- Version registry: `/opt/ai-starter-community/staging/course-editor/current/versions/index.json`
- Version storage: `/opt/ai-starter-community/staging/course-editor/current/versions/`
- Work copy: `/opt/ai-starter-community/staging/course-editor/current/work/`
- Export: `/opt/ai-starter-community/staging/course-editor/current/exports/openscript-universal-method-course-v04-edited.zip`

### Current restored editor state

- Version manager / dropdown restored to: `current`, `v01`, `v02`, `v03`, `edited`, `v04`
- The mistaken real-version deletion test reduced the registry to only `v001 / current`
- Safe source ZIPs were still present and were used for the restore
- Safe source ZIP recovery locations were `/tmp/course-editor-version-uploads/` and `/tmp/openscript-universal-method-course-*.zip`
- The restore was explicitly approved afterward and scoped only to the isolated editor registry/list
- No app source, production runtime, nginx/systemd, docs repo, or Agent Lab repo was touched by that restore
- The restore rebuilt the editor dropdown/list from safe ZIP sources

### Editor UI fixes already reported

- compact top editor menu
- removed Deleted / Edited counters from the top bar
- compact version dropdown
- readable dropdown options
- iframe height/layout fixed so the preview fills the viewport below the editor toolbar
- rendered asset resolution fixed by aliasing `/rendered/styles.css` and `/rendered/script.js` to the active worktree CSS/JS when needed

### Deletion semantics

- Menu deletion must delete only a managed editor version
- Menu deletion must remove the version record from `versions/index.json`
- Menu deletion must remove the managed copy under `versions/<id>/`
- Menu deletion must not delete uploaded source ZIPs in `/tmp/course-editor-version-uploads/`
- Menu deletion must not delete `/tmp/openscript-universal-method-course-*.zip`
- Menu deletion must not delete editor exports, the active work copy, app source, or production source/runtime
- Source ZIPs remaining after menu deletion is normal
- What must disappear after a successful menu deletion is the selected version from the editor dropdown and registry

### Current blocker

- Delete behavior after restore is still pending proof
- Future delete proof must use only a temporary managed `delete-test` version
- Real versions `current`, `v01`, `v02`, `v03`, `edited`, and `v04` must not be used for deletion tests again

### Current stop-point

- The isolated editor version manager is repaired and restored.
- The next safe step is safe delete proof with a temporary managed version only.
- Do not resume Kilo/design or production work automatically.
- Do not test delete on real versions.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260616_ISOLATED_COURSE_EDITOR_VERSION_MANAGER_REPAIR -->

<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_P0_AUTH_HARDENING_SOURCE_FIX_ACCEPTED source=codex_sync -->
## 2026-06-17 — P0 auth hardening source fix accepted

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community

### Accepted app source fix

- Branch: `fix/carousel-arrow-button-visuals`
- Commit: `80b8d44d28c21bf5e22cf1674e04c6f5bedcf95b`
- Commit title: `Harden login and session defaults`
- Changed files:
  - `source/app/auth/service.py`
  - `source/app/core/config.py`
  - `source/tests/test_auth_flow.py`

### Recorded result

- Login brute-force protection is now present.
- The failure policy is 5 failed attempts per 15 minutes.
- The attempt bucket is keyed by normalized email/login and stabilizes to `user:{id}` after lookup.
- Successful login clears the bucket.
- Session cookies now default secure in production/prod/staging while still allowing an explicit local/dev override via `SESSION_COOKIE_SECURE`.
- The Codex test run reported `uv run pytest tests/test_auth_flow.py -q` passed.
- The app backup used for rollback safety was local-only:
  - `backup/pre-p0-auth-security-fix-20260617-055351`
  - `/opt/ai-starter-community/.codex_backups/pre-p0-auth-security-fix-20260617-055351`

### Current limitation

- The login limiter is process-local in memory.
- That is a valid immediate P0 source hardening step, but it is not the final shared/distributed limiter design for multi-worker or restart-resistant deployments.

### Remaining security priorities

- P1: `password_secret` encryption design/proof with DB/state backup gate.
- P1: CSRF tokens for state-changing forms.
- P1/P2: `change_password()` session revocation behavior.
- P2: SQLite WAL / busy_timeout.
- P2: admin N+1 owner lookup.
- P2: duplicated account-block presentation/selection logic.
- P2: admin users pagination.

### Current stop-point

- P0 auth hardening source fix accepted.
- Next safe step: `password_secret_encryption_design_proof_with_db_backup_plan`.
- No production deployment was performed.
- No runtime state was mutated.
- No secrets were read or printed.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_P0_AUTH_HARDENING_SOURCE_FIX_ACCEPTED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED source=codex_sync -->
## 2026-06-17 — Phase 1 password-secret encryption source support accepted

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community

### Accepted app source fix

- Branch: `fix/carousel-arrow-button-visuals`
- Commit: `2b9e13c608c36cf4c44712f59b01dd396dbc17f2`
- Commit title: `Encrypt account block password secrets`
- Changed files:
  - `source/app/account_blocks/secret_crypto.py`
  - `source/app/account_blocks/service.py`
  - `source/app/core/config.py`
  - `source/tests/conftest.py`
  - `source/tests/test_account_blocks_service.py`
  - `source/tests/test_account_blocks_admin_ui.py`
  - `source/tests/test_account_blocks_cabinet_ui.py`
  - `source/pyproject.toml`
  - `source/uv.lock`

### Recorded result

- Phase 1 source-only encryption support is now implemented for `account_blocks.password_secret`.
- New and updated non-empty `password_secret` values are encrypted before storage.
- The envelope format is `enc:v1:<nonce_b64>.<ciphertext_b64>`.
- Encryption uses AES-GCM through `cryptography`.
- The nonce is freshly generated and 12 bytes long for each encryption.
- The dedicated runtime key env var is `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY`.
- The expected key format is a base64url-encoded 32-byte key.
- Legacy plaintext rows remain readable for backward compatibility.
- Authorized copy/UI behavior still returns the original secret after decrypt-on-read.
- Empty `password_secret` values remain supported.
- The Codex test run reported `uv run pytest tests/test_account_blocks_service.py tests/test_account_blocks_admin_ui.py tests/test_account_blocks_cabinet_ui.py tests/test_account_blocks_activation.py -q` passed.
- `uv lock --check` passed.
- The app commit was verified locally and on public GitHub.
- The local rollback backup was only inside `/opt/ai-starter-community/.codex_backups/pre-password-secret-encryption-phase1-20260617-065237`.

### Current limitation

- Existing live plaintext rows are not migrated in this source-only run.
- Runtime key provisioning is not proven by this docs run.
- Production deployment or restart is not proven by this docs run.
- Full at-rest protection for already stored plaintext contents still requires Phase 2 migration.
- Phase 2 migration requires a separate explicit run with a DB/state backup gate and rollback path.

### Remaining security priorities

- P1: Phase 2 migration of existing plaintext `password_secret` rows
- P1: CSRF tokens for state-changing forms
- P1/P2: `change_password()` should revoke active sessions or document the accepted behavior
- P2: SQLite WAL / busy_timeout hardening
- P2: admin N+1 owner lookup cleanup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination
- Informational/deployment: SQLite file permissions and server hardening

### Current stop-point

- Phase 1 source-only encryption support is accepted.
- Next safe step: `password_secret_phase2_migration_design_or_preflight_with_db_backup_gate`.
- Do not start production deployment, runtime mutation, Agent Lab work, or broader app fixes automatically.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED source=codex_sync -->
## 2026-06-17 — Password-secret Phase 2 DB migration completed in preview

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- Public app repo: https://github.com/MaksimUnimax/ai-starter-community

### Source / runtime baseline carried into migration

- App branch: `fix/carousel-arrow-button-visuals`
- Phase 1 source commit remains `2b9e13c608c36cf4c44712f59b01dd396dbc17f2`
- The preview runtime key `ACCOUNT_BLOCKS_PASSWORD_SECRET_KEY` was provisioned in `/etc/ai-starter-community/preview.env`
- The preview service `ai-starter-community-preview.service` had the key loaded from `EnvironmentFile` after restart

### Recorded migration result

- Preview DB path: `/opt/ai-starter-community/state/ai_starter_community.sqlite3`
- DB backup path: `/opt/ai-starter-community/state_backups/pre-password-secret-phase2-migration-20260617-081637/ai_starter_community.sqlite3`
- Pre-migration counts: total `8`, empty `2`, encrypted `0`, plaintext `6`, suspicious `0`
- Migration updated `6` legacy plaintext rows to `enc:v1:` envelopes
- Post-migration counts: total `8`, empty `2`, encrypted `6`, plaintext `0`, suspicious `0`
- Decrypt verification succeeded for `6` encrypted rows with `0` failures
- The targeted account-block tests passed again after the migration
- No app source commit was created in the migration run
- No production deployment or public handoff was performed

### Runtime remediation note

- The preview runtime venv initially lacked `cryptography`
- The runtime venv was synced with `cryptography==49.0.0` and its runtime deps so the preview service could restart successfully

### Current stop-point

- Phase 2 preview DB migration is complete
- Next safe step is `csrf_tokens_design_or_source_fix_with_backup`
- Do not start production deployment, Agent Lab work, or broader app fixes automatically
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_CSRF_SOURCE_FIX_ACCEPTED source=codex_sync -->
## 2026-06-17 — CSRF source fix accepted

### Accepted app source fix

- App repo: `/opt/ai-starter-community`
- Branch: `fix/carousel-arrow-button-visuals`
- Commit: `c0b4edf58bab56c2669229b873ab2348cea00c2b` — `Add CSRF protection for browser forms`
- Source-only browser-form CSRF protection is now implemented across auth, admin, user_cabinet, and public_landing surfaces.
- Shared helper: `source/app/shared/csrf.py`
- Hidden field name: `_csrf_token`
- Missing or invalid tokens return HTTP 403.
- 29 browser-form POST handlers are protected.
- Updated browser-flow tests: `source/tests/test_auth_flow.py`, `source/tests/test_account_blocks_admin_ui.py`, `source/tests/test_account_blocks_cabinet_ui.py`
- Dedicated CSRF tests: `source/tests/test_csrf_protection.py`
- Targeted pytest command passed in the app repo:
  - `cd /opt/ai-starter-community/source && uv run pytest tests/test_csrf_protection.py tests/test_auth_flow.py tests/test_account_blocks_service.py tests/test_account_blocks_admin_ui.py tests/test_account_blocks_cabinet_ui.py tests/test_account_blocks_activation.py -q`
- `git diff --check` passed.
- `python -m py_compile` on the modified source/tests passed.
- No runtime deployment/restart was performed in this docs sync.
- No DB mutation was performed in this docs sync.

### Current stop-point

- CSRF source fix is complete and recorded.
- Next safe step is `change_password_session_revocation_source_fix_with_backup`.
- Do not start runtime deployment, Agent Lab work, or broader app fixes automatically.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_CSRF_SOURCE_FIX_ACCEPTED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED source=codex_sync -->
## 2026-06-17 — Post-CSRF emergency fixes and materials public preview accepted

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: fix/carousel-arrow-button-visuals

### Recorded result

- Session revocation source fix accepted in app commit `e7fc37d272ca136418dd7e3a175cbbfb5bb03f96`.
- Emergency `/admin/users` 500 was fixed by restarting `ai-starter-community-preview.service` so the live process loaded the CSRF helper.
- Emergency `/` 500 was fixed in app commit `55ad86e6e1ff6b8dd7fbf015fd8e46e72390fa10`.
- Authenticated materials draft 500 was fixed in app commit `e29d591039c46fc4651f49281937f0dd564b8750`.
- Gated public preview for selected materials drafts was accepted in app commit `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928`.
- Current app HEAD after the public preview commit is `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928`.
- Preview smoke proof after the emergency fixes tested 30 GET URLs and reported `TOTAL_5XX: 0`.
- Public checks from the smoke proof recorded `/` `200`, `/admin/users` `303` to `/login`, unauthenticated materials draft `303` to `/login`, and health endpoints `200`.
- Authenticated materials coverage in the proof runs was provided by pytest fixtures; no browser cookies were used.
- No fresh tracebacks were found after the last restart/smoke.

### Important process note

- The session-revocation app-source run violated the strict pre-edit backup gate, but no rollback was performed and the source fix remains accepted because the scope was narrow, the public commit exists, tests passed, and no DB/runtime/docs/secrets/Agent Lab work was touched.

### Current stop-point

- Next safe step is `sqlite_wal_busy_timeout_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED source=codex_sync -->
## 2026-06-17 — SQLite WAL / busy_timeout source fix accepted, runtime apply pending

### Accepted app source fix

- App repo: `/opt/ai-starter-community`
- Branch: `fix/carousel-arrow-button-visuals`
- Commit: `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- Changed files:
  - `source/app/shared/db.py`
  - `source/tests/test_db_connection_pragmas.py`
- `source/app/shared/db.py` now centralizes SQLite connection hardening with `SQLITE_BUSY_TIMEOUT_MS = 5000`.
- App-created file-backed SQLite connections now apply `PRAGMA busy_timeout = 5000`, `PRAGMA foreign_keys = ON`, and `PRAGMA journal_mode = WAL`.
- In-memory databases (`:memory:`, `file::memory:`, and URI memory mode) skip WAL and parent-directory creation but still get busy timeout and foreign-key setup.
- `get_connection()` and `initialize_database()` use the same shared helper.
- New test coverage in `source/tests/test_db_connection_pragmas.py` proved file-backed WAL/busy_timeout behavior and safe in-memory handling.
- Targeted `py_compile` and pytest checks passed in the source run.
- The source fix is accepted and pushed, but it is not yet active in the running preview process because runtime restart/reload has not happened.
- Live DB was not touched; no manual SQLite PRAGMA was run against the live preview database.
- No schema migration, runtime config change, or Agent Lab work was performed.

### Runtime boundary

- `RUNTIME_NOT_APPLIED_YET: yes`
- `FIRST_RUNTIME_APPLY_REQUIRES_DB_STATE_BACKUP: yes`
- `MANUAL_LIVE_DB_PRAGMA_REQUIRED: no`
- The first future runtime apply/restart will cause the app to open the file-backed SQLite DB and execute `PRAGMA journal_mode = WAL`.
- WAL activation can mutate SQLite state or create WAL-related sidecar files, so the first runtime apply/restart must be DB/state backup-gated.

### Current stop-point

- SQLite WAL / busy_timeout source fix is complete in source.
- Next safe step is `sqlite_wal_busy_timeout_runtime_apply_with_db_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED source=codex_sync -->
## 2026-06-17 — SQLite WAL / busy_timeout runtime applied accepted

### Runtime apply proof

- Repo: `/opt/ai-starter-community`
- Branch: `fix/carousel-arrow-button-visuals`
- App commit at runtime apply: `3ffd6c9ec2af4b585d94479259c7770c21ce6778`
- Service: `ai-starter-community-preview.service`
- Service state before: `active (running)`
- Service MainPID before: `3087767`
- DB/state backup gate passed before restart.
- DB backup dir: `/opt/ai-starter-community/state_backups/pre-sqlite-wal-runtime-apply-20260617-140653`
- Backed up DB file: `ai_starter_community.sqlite3`
- Before restart, WAL/SHM files were absent.
- Service was restarted and is now active running with MainPID `3106155`.
- A new app-style SQLite connection via `source/app/shared/db.py:get_connection()` reported `busy_timeout = 5000`, `journal_mode = wal`, and `foreign_keys = 1`.
- After restart, `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm` are present.
- GET-only smoke tested 30 URLs and reported `TOTAL_5XX: 0`.
- No new traceback or `database is locked` errors were observed after restart.

### Runtime boundary now closed

- The first runtime application of the SQLite WAL / busy_timeout source fix has completed safely.
- No manual live DB PRAGMA or migration was required.
- No source, docs, config, or Agent Lab changes were performed in the runtime apply run.

### Current stop-point

- SQLite WAL / busy_timeout runtime application is complete and active in preview.
- Next safe step is `admin_n_plus_one_owner_lookup_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED -->
<!-- CONTEXT_APPEND_BEGIN id=CTX_SITE_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED source=codex_sync -->
## 2026-06-18 — Security/performance backlog completed and preview runtime applied

### Current project

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: fix/carousel-arrow-button-visuals

### Accepted app commits

- `49c9ef228ee7a5f37ac1dc8da581291856cfa044` — `Avoid admin owner lookup N+1`
- `44d7893428beb55f50b1cd538e842660d59d194a` — `Cover missing-owner admin account block lookup edge`
- `7f054551aad5a6b4e7c2c6f58dfd5f9ad48eb17b` — `Consolidate account block presentation logic`
- `9caf6f08579ccbd01ba1cf730347fe36e552d519` — `Add pagination to admin users`

### Current live state summary

- Admin account-block owner lookup N+1 cleanup is complete; preview runtime uses the bulk owner lookup and bulk copy-data helper.
- Missing-owner mail-block edge is fixed; the admin list no longer falls back to per-row owner lookup after a bulk miss.
- Account-block presentation/selection logic is consolidated in shared helpers used by admin and cabinet routes.
- Admin users pagination is live with bounded `COUNT(*)`/`LIMIT`/`OFFSET` queries and preserved filters.
- The preview runtime restart after `7f05455...` also applied the earlier account-block source fixes and reported a 30-URL smoke with `TOTAL_5XX: 0`.
- The final runtime restart after `9caf6f...` tested 32 GET URLs and reported `TOTAL_5XX: 0`.
- Service `ai-starter-community-preview.service` is active.
- Latest runtime MainPID: `3157141`.
- No new traceback or `database is locked` errors were observed after the final restart.

### Current completion state

- Tracked security/performance backlog: completed and accepted.
- Current remaining security/performance backlog: none.
- Production/public handoff remains separate and requires explicit approval.

### Current stop-point

- The remaining tracked security/performance backlog is complete and recorded.
- Next safe step is `final_security_performance_review_or_next_product_step`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- CONTEXT_APPEND_END id=CTX_SITE_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED -->
