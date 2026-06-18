# Roadmap v0.1 — Initial site baseline

STATUS: INITIAL_SOURCE_DERIVED_BASELINE
PROJECT: OpenScript / AI Starter Community
RUN_ID: site-docs-initial-import-20260531
DATE: 2026-05-31

## Stage 0: Repo separation and AGENTS bootstrap (completed)

- [x] Repository separation proof (site-repo-separation-proof-20260531)
- [x] Root AGENTS.md contracts created (site-agents-bootstrap-20260531)
- [x] Docs repo currentized, legacy Agent Lab marked (site-docs-currentization-repair-20260531)

## Stage 1: Site docs currentization and source-derived baseline (completed)

- [x] Initial source-derived documentation baseline (site-docs-initial-import-20260531)
- [x] Staging design proof (site-staging-design-only-20260531)
- [x] Staging implementation (site-staging-implementation-20260531)
- [x] Staging policy correction (site-staging-policy-correction-20260531)

## Stage 2: Isolated staging/test contour (completed and health-proven)

- [x] Design test/staging environment
- [x] Create isolated runtime with test data
- [x] Prove staging does not touch production
- [x] Write staging proof docs
- [x] Staging runtime health proven (site-staging-health-proof-20260531)
- [x] healthz: {"ok":true,"service":"ai-starter-community"}
- [x] readyz: {"ok":true,"ready":true}
- [x] Listener: 127.0.0.1:8090 only
- [x] Process stopped after proof
- [x] Port 8090 free after stop

## Stage 3: Design/Kilo workflow on staging (next)

- [ ] Establish Kilo-safe design workflow using the staging environment
- [ ] First design/implementation run targeting a narrow bounded scope
- [ ] Each run proves staging isolation before source changes

## Stage 4: Manual review and screenshot proof (later)

- [ ] Design review via screenshots or browser proof
- [ ] Manual approval before staging-to-production handoff

## Stage 5: Production handoff (later, separate approval)

- [ ] Production deployment only after explicit manual approval
- [ ] No production changes without a completed docs gate, staging proof, and manual approval

## Known blockers (not yet started)

- Design/Kilo workflow configuration not yet defined
- Screenshot/review method not yet decided
- Payments and AI Sales Agent modules have structure but implementation NOT_YET_PROVEN

## 2026-06-03 — Course lessons 1–9 semantic blocks accepted

### Append id

- RM_SITE_COURSE_LESSONS_20260603

### Current completed stage

- Course “Работа с ИИ” lesson content and UI-structure refinement on branch `design/product-story-03`
- Lessons 1–9 were converted into semantic blocks/cards
- Lesson 4 keeps the starter prompt controls and the corrected deploy-key flow
- The final accepted app commit is `a5a2f6ef40338959a659bc9feecf0a23c46a0c70`
- Public GitHub showed 1 file changed, 916 additions, 10 deletions

### Next

- Docs currentization is being completed now
- Then wait for the user-selected next site/course task

### Not current

- Kilo/design workflow is historical unless the user explicitly selects Kilo
- Production deployment remains a separate later concern
- Payments and AI Sales Agent remain not yet proven

<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY source=codex_sync accepted_by_user=yes -->

## 2026-06-05 — Course lesson 7 rewrite accepted; design preflight is next

### Source

- OpenScript / AI Starter Community
- Docs repo: /opt/openscript-site-docs
- App repo: /opt/ai-starter-community
- App branch: design/product-story-03

### Current accepted app state

- Latest accepted course app commit: f6f5c2b100296efd69c67fa7387550cf2595340d
- Commit title: Rewrite lesson 7 process workflow
- Changed files:
  - source/app/materials/course_content/drafts/dair_smoke_20260529/index.html
  - source/app/materials/course_content/drafts/dair_smoke_20260529/script.js
  - source/tests/test_course_rendering.py

### Accepted course state

- Lesson 7 is now "Процесс работы".
- Lesson 7 covers run definition, one run usually solving one task for control, Design run, Fix run, Proof run, context and context window, prefix-extension / Project Prefixer practice, student-kit link, and an updated quiz.
- Lesson 6 next link now points to Lesson 7 "Процесс работы".

### Current stage summary

- Stage 0 — Repo separation and AGENTS bootstrap: COMPLETED
- Stage 1 — Site docs currentization and source-derived baseline: COMPLETED
- Stage 2 — Isolated staging/test contour: COMPLETED and HEALTH-PROVEN
- Stage 2.5 — Course lesson refinement on design/product-story-03: COMPLETED through f6f5c2b100296efd69c67fa7387550cf2595340d
- Stage 3 — Design/Kilo workflow preflight on staging: NEXT
- Stage 4 — Manual review and screenshot proof: LATER
- Stage 5 — Production handoff: LATER, separate approval required

### Current stop-point

- Course lesson refinement is accepted through app commit f6f5c2b100296efd69c67fa7387550cf2595340d.
- Staging/test contour is already health-proven.
- Next safe technical run is site-design-workflow-preflight-20260605.
- Run mode: design-workflow-proof / no app UI changes yet

### Not next

- production deploy
- payment implementation
- AI Sales Agent implementation
- Agent Lab work
- app refactor
- nginx/systemd
- public staging exposure
- direct UI patch without design workflow preflight

<!-- ROADMAP_APPEND_END id=RM_SITE_20260605_COURSE_ACCEPTED_AND_DESIGN_PREFLIGHT_READY -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION source=codex_sync accepted_by_user=yes -->

## 2026-06-09 — Cabinet account-blocks and paid-options live iteration

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the latest live cabinet iteration.
- App repo branch remains `design/product-story-03`.
- Paid-options cabinet block is live and shows active add-ons from the database.
- Base AI / GPT tool option is hidden from the add-on activation block.
- Add-ons are ordered by price descending.
- Buy remains a safe placeholder; real payment processing is still not implemented.
- Server-backed account blocks are live in `/cabinet`.
- LocalStorage is no longer the source of truth for account blocks.
- Account block types supported in UI: ChatGPT, Сервер, Почта.
- Owner is resolved server-side and hidden from the visible UI.
- Manual title and email fields were removed from the account block UI.
- Admin and moderator can create, edit, delete, and activate account blocks.
- Moderator does not gain full admin dashboard rights.
- Activation email is wired to the owner user's registered email.
- Activation text uses elapsed-day wording, not remaining-days wording.
- Account actions use fetch-based no-jump handling and preserve scroll position.
- Account cards use bounded tracks and do not stretch full width on desktop/tablet when only one card is visible.
- Production test-user cleanup was completed with a backup before deletion.

### Current completion state

- Paid-options cabinet block live iteration: completed technically, manual browser verification pending
- Account-block backend/UI live iteration: completed technically, manual browser verification pending
- Moderator assignment live iteration: completed technically
- Activation email live iteration: completed technically
- No-jump and bounded-width cabinet UX: completed technically, manual browser verification pending
- Production test-user cleanup: completed technically

### Open follow-ups

- Manual browser verification of the latest no-jump/card-width/account-email behavior
- Real payment processing / entitlement flow
- Password-secret encryption or other secret-storage policy decision

### Not current

- Kilo/design workflow preflight as the active app task
- Payment provider implementation
- Any app repo or runtime change in this docs run
- Agent Lab work

<!-- ROADMAP_APPEND_END id=RM_SITE_20260609_CABINET_ACCOUNT_BLOCKS_PAID_OPTIONS_LIVE_ITERATION -->

<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION source=codex_sync -->

## 2026-06-10 — Course carousels and VPN account-block iteration

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the latest course and cabinet iteration.
- App repo branch remains `design/product-story-03`.
- Course practical carousels are implemented in the current course memory:
  - lesson 3 Git real screenshot carousel from static assets;
  - lesson 6 project-start placeholder carousel;
  - lesson 7 prefix-extension placeholder carousel;
  - lesson 8 docs update / new-dialog placeholder carousel pattern.
- VPN is a real account-block type; login/password are not required.
- VPN video asset is `/static/videos/amnezia-vpn-guide.mp4`.
- The polished VPN panel with Tech Talk attribution and a normal-sized Amnezia button is reported as feature/live-synced state; if not already fast-forwarded into the active branch, treat it as pending branch integration.

### Current completion state

- Course practical carousels currentization: completed technically, manual browser verification pending
- VPN real account-block type: completed technically, manual browser verification pending
- VPN separate collapsible block after Accounts: pending / not yet proven
- Real payment processing: still NOT_YET_PROVEN
- Password-secret policy: still open

### Current stop-point

- Manual browser verification of the latest course carousel and VPN cabinet behavior is still pending unless explicitly confirmed by the user.

### Next phase

- `manual_browser_verification_pending_for_course_carousels_and_vpn_block`

### Later phase after screenshots

- Replace placeholder carousels with real screenshots where they are still pending.
- Continue with real payment provider implementation and password-secret policy decision as separate follow-up work.

### Not current

- Kilo/design workflow is not the current active task unless the user explicitly selects it.
- Payment provider implementation is not the current run.
- Agent Lab is not the current project for this docs repo.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260610_COURSE_CAROUSELS_AND_VPN_ACCOUNT_BLOCK_ITERATION -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-14 — Course lesson 4/5 and admin export repair: COMPLETED and ACCEPTED

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the accepted lesson 4/5 wording and the accepted admin course ZIP export state.
- App repo branch remains `design/product-story-03`.
- Lesson 4 title is now `Codex, AGENTS.md, токены и роль модели`.
- Lesson 4 accepted visible content no longer shows `Skills`, `Skill`, `/skills`, `plugins`, `plugin`, or `/plugins`.
- Lesson 4 uses approved `рабочий шаг (run)` wording and `лимиты ресурсов`.
- Lesson 4 slash-command section now teaches only `/status`, `/model`, and `/permissions`, plus the slash-menu explanation.
- Lesson 5 links `личный кабинет курса` and grammatical variants to `https://openscript.ru/cabinet` with `target="_blank"` and `rel="noreferrer"`.
- Admin course export route is `/admin/course-export`.
- ZIP export is accepted with 72 entries, 51 carousel assets, 2 hero images, and 3 prompt markdown files.
- The exported manifest is sanitized and no longer leaks absolute server paths.

### Accepted prompt files

- `prompts/01-start-project-documentation.md`
- `prompts/02-project-docs-update.md`
- `prompts/03-new-project-dialogue.md`

### Current completion state

- Course lesson 4/5 wording repair: completed and accepted
- Admin course ZIP export repair: completed and accepted
- Manifest sanitization: completed and accepted
- App repo changes are already accepted in the app task; this docs repo update only records the accepted state

### Current stop-point

Course lesson 4/5 wording and the admin course ZIP export are accepted. The export now contains course text/source, all referenced carousel assets, hero images, three course prompt markdown files, and a sanitized manifest. Next safe step is the next explicit user-selected task. Do not start payment, production, Agent Lab, or broad app refactor automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260614_COURSE_LESSON_4_5_AND_ADMIN_EXPORT_ACCEPTED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260615_PUBLIC_TARIFF_ACCESS_UI_ITERATION_ACCEPTED source=codex_sync -->

## 2026-06-15 — Public tariff/access UI iteration accepted

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the accepted live public tariff/access UI iteration.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted/deployed commit: `eb22b091a2a732966c62e24a93c1799babc3440f` — Keep tariff edit page and scale card typography.
- Earlier typography-control commit: `8a905300739c833ee46ad06383a76d6e65e1c489` — Add tariff typography controls.
- Tariff admin now supports source-backed order, selected-card alignment, and safe integer px typography controls.
- Tariff edit save stays on the same edit page with the notice `Изменения сохранены.`
- New tariff creation redirects to the new tariff edit page with the notice `Тариф создан.`
- Selected tariff cards render through the shared pricing partial with safe CSS variables and font-size-aware rows, so large typography does not overlap the description.
- Public/authenticated UI and cabinet access-gate recovery remain part of the accepted live state.
- Real payment remains NOT_YET_PROVEN.

### Current completion state

- Public tariff/access/UI recovery: completed technically, deployed, and accepted
- Tariff typography controls: completed technically, deployed, and accepted
- Same-page tariff edit save behavior: completed technically, deployed, and accepted
- Real payment processing: still NOT_YET_PROVEN

### Current stop-point

- The live public tariff/access/UI iteration is accepted and deployed. Next safe step is the next explicit user-selected task.

### Not current

- Do not infer payment or Agent Lab work automatically.
- Do not treat the earlier course-export stop-point as current.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260615_PUBLIC_TARIFF_ACCESS_UI_ITERATION_ACCEPTED -->

<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260616_ISOLATED_COURSE_EDITOR_VERSION_MANAGER_REPAIR source=codex_sync accepted_by_user=yes -->

## 2026-06-16 — Isolated course editor version manager repaired and restored

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the explicit user-selected isolated course editor tooling repair/restoration task.
- The isolated course editor is under `/opt/ai-starter-community/staging/course-editor/current/` and is not production app source.
- The editor version manager / dropdown was restored from safe ZIP sources to `current`, `v01`, `v02`, `v03`, `edited`, and `v04`.
- The previous mistaken real-version deletion test reduced the registry to only `v001 / current`; that was a process mistake.
- Safe source ZIPs remained available and were used for the restore.
- Safe source ZIP recovery locations were `/tmp/course-editor-version-uploads/` and `/tmp/openscript-universal-method-course-*.zip`.
- The restore was later explicitly approved and scoped only to the isolated editor registry/list.
- No app source, production runtime, nginx/systemd, docs repo, or Agent Lab repo was touched by that restore.

### Completed

- version dropdown restored from safe ZIP sources
- compact top editor menu and compact version dropdown reported as accepted fixes
- Deleted / Edited counters removed from the top bar
- readable dropdown options
- iframe height/layout fixed so the preview fills the viewport below the editor toolbar
- rendered CSS/JS aliases fixed for `/rendered/styles.css` and `/rendered/script.js`

### Pending

- safe delete proof using a temporary managed `delete-test` version only

### Not current

- production deploy
- payment implementation
- Agent Lab work
- app refactor
- Kilo/design preflight unless explicitly selected
- real-version deletion tests

### Current stop-point

- The isolated editor version manager repair/restore is complete.
- Next safe step is `course_editor_safe_delete_proof_with_temporary_version`.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260616_ISOLATED_COURSE_EDITOR_VERSION_MANAGER_REPAIR -->

<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_P0_AUTH_HARDENING_SOURCE_FIX_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — P0 auth hardening source fix accepted

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the accepted P0 auth hardening source fix.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commit: `80b8d44d28c21bf5e22cf1674e04c6f5bedcf95b` — `Harden login and session defaults`
- Changed files:
  - `source/app/auth/service.py`
  - `source/app/core/config.py`
  - `source/tests/test_auth_flow.py`
- Login brute-force protection now exists in the app source.
- Failure policy: 5 failed attempts per 15 minutes.
- The limiter is keyed by normalized email/login and stabilizes to `user:{id}` once the user is known.
- Successful login clears the failure bucket.
- Session cookies now default secure in production/prod/staging.
- `SESSION_COOKIE_SECURE` still allows an intentional local/dev override.

### Current completion state

- Login brute-force protection hardening: completed technically and accepted
- Production-safe secure-cookie default: completed technically and accepted
- Targeted auth tests: passed (`uv run pytest tests/test_auth_flow.py -q`)
- Production deployment: not performed
- Runtime state: not mutated

### Open follow-ups

- P1: `password_secret` encryption design/proof with DB/state backup gate
- P1: CSRF tokens for state-changing forms
- P1/P2: `change_password()` session revocation behavior
- P2: SQLite WAL / busy_timeout
- P2: admin N+1 owner lookup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination
- Limiter design follow-up: process-local in-memory rate limiting is acceptable for the immediate P0 fix but not the final multi-worker/shared-store design

### Current stop-point

- The P0 auth hardening source fix is accepted.
- Next safe step is `password_secret_encryption_design_proof_with_db_backup_plan`.
- Do not start production deployment, runtime mutation, Agent Lab work, or broad app refactor automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_P0_AUTH_HARDENING_SOURCE_FIX_ACCEPTED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — Password-secret encryption Phase 1 source-only support accepted

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the accepted Phase 1 source-only encryption support for `account_blocks.password_secret`.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commit: `2b9e13c608c36cf4c44712f59b01dd396dbc17f2` — `Encrypt account block password secrets`
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
- New and updated non-empty `password_secret` values are now encrypted before storage.
- The envelope format is `enc:v1:<nonce_b64>.<ciphertext_b64>`.
- Encryption uses AES-GCM through `cryptography`.
- Legacy plaintext rows remain readable for backward compatibility.
- Empty `password_secret` values remain supported.

### Current completion state

- Phase 1 source-only password-secret encryption support: completed technically and accepted
- Targeted account-block tests: passed (`uv run pytest tests/test_account_blocks_service.py tests/test_account_blocks_admin_ui.py tests/test_account_blocks_cabinet_ui.py tests/test_account_blocks_activation.py -q`)
- Dependency lock check: passed (`uv lock --check`)
- Production deployment: not performed
- Runtime state: not mutated
- Live DB migration: not performed

### Open follow-ups

- P1: Phase 2 migration of existing plaintext `password_secret` rows with a separate DB/state backup gate
- P1: CSRF tokens for state-changing forms
- P1/P2: `change_password()` session revocation behavior
- P2: SQLite WAL / busy_timeout
- P2: admin N+1 owner lookup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination
- Runtime key provisioning: not proven by this docs run

### Current stop-point

- Phase 1 password-secret encryption source support is accepted.
- Next safe step is `password_secret_phase2_migration_design_or_preflight_with_db_backup_gate`.
- Do not start production deployment, runtime mutation, Agent Lab work, or broader app refactors automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_PASSWORD_SECRET_ENCRYPTION_PHASE1_SOURCE_ACCEPTED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — Password-secret Phase 2 preview DB migration completed

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the completed preview DB migration of `account_blocks.password_secret`.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Phase 1 source commit remains `2b9e13c608c36cf4c44712f59b01dd396dbc17f2`.
- The preview runtime key was provisioned in `/etc/ai-starter-community/preview.env`.
- The preview service `ai-starter-community-preview.service` restarted and is active.
- The preview runtime venv had to be synced with `cryptography==49.0.0` and runtime deps because it initially lacked the dependency.
- No app source commit was created in the migration run.
- No production deployment or public handoff was performed.

### Migration result

- DB backup path: `/opt/ai-starter-community/state_backups/pre-password-secret-phase2-migration-20260617-081637/ai_starter_community.sqlite3`
- Pre-migration counts: total `8`, empty `2`, encrypted `0`, plaintext `6`, suspicious `0`
- `6` legacy plaintext rows were migrated to `enc:v1:` envelopes.
- Post-migration counts: total `8`, empty `2`, encrypted `6`, plaintext `0`, suspicious `0`
- Decrypt verification: `6` success / `0` failure
- DB backup integrity was verified and counts matched before migration.

### Current completion state

- Phase 2 preview DB migration for `password_secret`: completed technically and accepted
- Targeted account-block tests: passed (`cd /opt/ai-starter-community/source && uv run pytest tests/test_account_blocks_service.py tests/test_account_blocks_admin_ui.py tests/test_account_blocks_cabinet_ui.py tests/test_account_blocks_activation.py -q`)
- Production deployment: not performed
- Runtime state: mutated only in preview DB / preview runtime
- Live DB migration: completed in preview only

### Open follow-ups

- P1: CSRF tokens for state-changing forms
- P1/P2: `change_password()` session revocation behavior
- P2: SQLite WAL / busy_timeout
- P2: admin N+1 owner lookup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination
- Runtime key provisioning: complete for preview; production still needs separate approval and rollout

### Current stop-point

- Phase 2 preview DB migration is complete.
- Next safe step is `csrf_tokens_design_or_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app refactors automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_PASSWORD_SECRET_PHASE2_DB_MIGRATION_COMPLETED -->

<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_CSRF_SOURCE_FIX_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — CSRF source fix accepted

### Current source / live state

- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commit: `c0b4edf58bab56c2669229b873ab2348cea00c2b` — `Add CSRF protection for browser forms`.
- CSRF protection for browser forms is implemented as a source-only fix across auth, admin, user_cabinet, and public_landing.
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

### Current completion state

- CSRF source fix: completed technically and accepted
- Production deployment: not performed
- Runtime state: not mutated in this docs sync
- Preview/runtime rollout for CSRF: not recorded as done

### Open follow-ups

- P1/P2: `change_password()` session revocation behavior
- P2: SQLite WAL / busy_timeout
- P2: admin N+1 owner lookup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination

### Current stop-point

- CSRF source fix is complete and recorded.
- Next safe step is `change_password_session_revocation_source_fix_with_backup`.
- Do not start runtime deployment, Agent Lab work, or broader app refactors automatically.

<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_CSRF_SOURCE_FIX_ACCEPTED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — Post-CSRF emergency fixes and materials public preview accepted

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the accepted session-revocation source fix, the emergency runtime 500 fixes, the materials CSRF helper fix, and the gated public materials preview state.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commits:
  - `e7fc37d272ca136418dd7e3a175cbbfb5bb03f96` — Revoke sessions on password change
  - `55ad86e6e1ff6b8dd7fbf015fd8e46e72390fa10` — Fix public landing template request context
  - `e29d591039c46fc4651f49281937f0dd564b8750` — Register CSRF helper for materials templates
  - `b9e928b77ccc1dedf92ea28e85d3e1f96dedf928` — Add gated public preview for selected materials drafts
- `change_password()` now revokes active sessions on password change and forces re-login.
- The emergency `/admin/users` 500 was fixed by restarting only `ai-starter-community-preview.service` so the live process loaded the CSRF helper.
- The emergency `/` 500 was fixed in source by removing the duplicate `request` argument from the public landing template helper.
- Authenticated materials draft pages stopped 500ing after the materials Jinja environment registered the shared CSRF helper.
- Gated public preview for selected materials drafts is disabled by default, keyed by `APP_ENV=staging` plus `STAGING_PUBLIC_COURSE_PREVIEW`, and limited to the explicit allowlist:
  - `/materials/drafts/dair-smoke-20260529/`
  - `/materials/drafts/dair-smoke-20260529/styles.css`
  - `/materials/drafts/dair-smoke-20260529/script.js`
- The public preview bypass applies only to GET/HEAD. Unsafe methods remain protected.
- Preview smoke proof after the emergency fixes tested 30 GET URLs and reported `TOTAL_5XX: 0`.
- Public checks from the smoke proof recorded `/` `200`, `/admin/users` `303` to `/login`, unauthenticated materials draft `303` to `/login`, and health endpoints `200`.
- `ai-starter-community-preview.service` is active.
- Authenticated materials coverage in the proof runs was provided by pytest fixtures; no browser cookies were used.
- No fresh tracebacks were observed after the last restart/smoke.

### Process note

- The session-revocation app-source run violated the strict pre-edit backup gate, but no rollback was performed and the source fix remains accepted because the scope was narrow, the public commit exists, tests passed, and no DB/runtime/docs/secrets/Agent Lab work was touched.

### Current completion state

- Session revocation source fix: completed and accepted
- Emergency `/admin/users` runtime fix: completed and accepted
- Emergency `/` source fix: completed and accepted
- Materials CSRF helper source fix: completed and accepted
- Gated public preview for selected materials drafts: completed and accepted
- Preview runtime smoke proof: completed with `TOTAL_5XX: 0`

### Open follow-ups

- P2: SQLite WAL / busy_timeout
- P2: admin N+1 owner lookup
- P2: duplicated account-block presentation/selection logic
- P2: admin users pagination
- Production/public handoff remains separate and requires explicit approval

### Current stop-point

- The post-CSRF emergency fixes and materials public preview state are recorded.
- Next safe step is `sqlite_wal_busy_timeout_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_POST_CSRF_EMERGENCY_FIXES_AND_MATERIALS_PREVIEW_ACCEPTED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — SQLite WAL / busy_timeout source fix accepted, runtime apply pending

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the accepted SQLite WAL / busy_timeout source fix on the main app repo.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commit:
  - `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- `source/app/shared/db.py` now centralizes SQLite connection hardening.
- `SQLITE_BUSY_TIMEOUT_MS = 5000`.
- File-backed app SQLite connections now apply:
  - `PRAGMA busy_timeout = 5000`
  - `PRAGMA foreign_keys = ON`
  - `PRAGMA journal_mode = WAL`
- In-memory SQLite connections skip WAL and parent-directory creation safely while still applying busy timeout and foreign-key setup.
- The source fix is accepted and pushed.
- The running preview process has not yet been restarted or reloaded for this source fix.
- Live DB was not touched and no manual live SQLite PRAGMA was run in the source-only app fix.
- No schema migration or runtime config change was performed in the app source run.

### Proof

- New test file: `source/tests/test_db_connection_pragmas.py`
- Targeted coverage proved:
  - file-backed temp DB gets busy_timeout and WAL;
  - in-memory DB skips WAL safely;
  - existing targeted auth/CSRF/routes/materials/account-block tests still passed.
- `python -m py_compile app/shared/db.py tests/test_db_connection_pragmas.py` passed.
- `uv run pytest tests/test_db_connection_pragmas.py tests/test_auth_flow.py tests/test_csrf_protection.py tests/test_routes.py tests/test_materials_flow.py tests/test_account_blocks_service.py tests/test_account_blocks_admin_ui.py tests/test_account_blocks_cabinet_ui.py tests/test_account_blocks_activation.py -q` passed.

### Runtime boundary

- The first future runtime apply/restart will open the file-backed SQLite DB and execute `PRAGMA journal_mode = WAL`.
- Because WAL activation can mutate SQLite state and create WAL-related sidecar files, the first runtime apply/restart must be guarded by a DB/state backup.
- Manual live DB PRAGMA is not required by the source fix.

### Current completion state

- SQLite WAL / busy_timeout source fix: completed and accepted
- Runtime application: not yet applied
- Production/public handoff: separate and still unproven

### Open follow-ups

- admin N+1 owner lookup cleanup
- duplicated account-block presentation/selection logic
- admin users pagination
- runtime apply/restart for SQLite WAL hardening with DB/state backup gate

### Current stop-point

- Source fix is complete and recorded.
- Next safe step is `sqlite_wal_busy_timeout_runtime_apply_with_db_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_SOURCE_FIX_ACCEPTED_RUNTIME_NOT_APPLIED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-17 — SQLite WAL / busy_timeout runtime applied accepted

### Current source / live state

- OpenScript / AI Starter Community docs repo now records that the preview runtime has applied the accepted SQLite WAL / busy_timeout source fix safely.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commit:
  - `3ffd6c9ec2af4b585d94479259c7770c21ce6778` — `Configure SQLite WAL and busy timeout`
- Runtime apply used the backup gate before restarting `ai-starter-community-preview.service`.
- DB/state backup dir:
  - `/opt/ai-starter-community/state_backups/pre-sqlite-wal-runtime-apply-20260617-140653`
- Backed up DB file:
  - `ai_starter_community.sqlite3`
- Before restart, `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm` were absent.
- After restart, both `ai_starter_community.sqlite3-wal` and `ai_starter_community.sqlite3-shm` are present.
- Runtime PRAGMA proof from an app-style connection reported:
  - `PRAGMA busy_timeout = 5000`
  - `PRAGMA journal_mode = wal`
  - `PRAGMA foreign_keys = 1`
- GET-only smoke after restart tested 30 URLs and reported `TOTAL_5XX: 0`.
- No `database is locked` errors or new tracebacks were observed after restart.
- No source modification, docs modification, config modification, DB migration, rollback, restore, or Agent Lab work was performed in the runtime apply run.

### Completion state

- SQLite WAL / busy_timeout runtime application: completed and accepted
- Runtime deployment boundary for this source fix: closed
- Production/public handoff remains separate and requires explicit approval

### Open follow-ups

- admin N+1 owner lookup cleanup
- duplicated account-block presentation/selection logic
- admin users pagination

### Current stop-point

- SQLite WAL / busy_timeout source fix and runtime application are both complete and recorded.
- Next safe step is `admin_n_plus_one_owner_lookup_source_fix_with_backup`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260617_SQLITE_WAL_BUSY_TIMEOUT_RUNTIME_APPLIED_ACCEPTED -->
<!-- ROADMAP_APPEND_BEGIN id=RM_SITE_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED_ACCEPTED source=codex_sync accepted_by_user=yes -->

## 2026-06-18 — Security/performance backlog completed and preview runtime applied

### Current source / live state

- OpenScript / AI Starter Community docs repo is currentized for the completed remaining security/performance backlog fixes on the main app repo.
- App repo branch remains `fix/carousel-arrow-button-visuals`.
- Latest accepted app commits:
  - `49c9ef228ee7a5f37ac1dc8da581291856cfa044` — `Avoid admin owner lookup N+1`
  - `44d7893428beb55f50b1cd538e842660d59d194a` — `Cover missing-owner admin account block lookup edge`
  - `7f054551aad5a6b4e7c2c6f58dfd5f9ad48eb17b` — `Consolidate account block presentation logic`
  - `9caf6f08579ccbd01ba1cf730347fe36e552d519` — `Add pagination to admin users`
- The tracked security/performance backlog is now complete:
  - admin N+1 owner lookup
  - missing-owner edge fix
  - account-block presentation/selection consolidation
  - admin users pagination
- The preview runtime restart after `7f05455...` also applied the earlier account-block source fixes and reported a 30-URL smoke with `TOTAL_5XX: 0`.
- The final preview runtime restart after `9caf6f...` reported a 32-URL smoke with `TOTAL_5XX: 0`.
- No new traceback or `database is locked` errors were observed after the final restart.
- Current remaining tracked security/performance backlog: none.
- Production/public handoff remains separate and requires explicit approval.

### Current stop-point

- The tracked security/performance backlog is complete and recorded.
- Next safe step is `final_security_performance_review_or_next_product_step`.
- Do not start production deployment, Agent Lab work, or broader app fixes automatically.
<!-- ROADMAP_APPEND_END id=RM_SITE_20260618_SECURITY_PERFORMANCE_BACKLOG_COMPLETED_RUNTIME_APPLIED_ACCEPTED -->
