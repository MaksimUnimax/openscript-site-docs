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
